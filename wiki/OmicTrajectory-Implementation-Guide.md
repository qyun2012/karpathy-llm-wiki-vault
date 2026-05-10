---
title: "Omic轨迹医学的实施算法与决策框架"
type: concept
aliases: ["轨迹医学算法", "纵向Omic对标", "AI轨迹监测系统"]
tags: [precision-medicine, AI-algorithm, trajectory-medicine, omic-analysis, decision-support]
sources: [
  "wiki/synthesis-ibd-omics-intelligence-loop.md",
  "wiki/concepts/OmicTrajectory.md",
  "wiki/concepts/TherapeuticResponseTrajectory.md"
]
last_updated: 2026-04-29
---

# Omic轨迹医学的实施算法与决策框架

## 核心理念

**Omic轨迹医学** 不是诊断患者"属于哪一类"，而是追踪患者在多维分子空间中的**动态演化曲线**，并通过AI实时对标预期轨迹，识别偏离并触发针对性干预。

```
传统：基线 → 分类 → 一次性治疗决策
轨迹：基线 → 建立预期曲线 → 周期监测 → 实时对标 → 动态干预
```

---

## I. 数据层：多维Omic空间的建立

### 1.1 四维Omic坐标系的定义

每个患者在 $t$ 时刻的状态表示为4维向量：

$$\mathbf{O}_i(t) = (T_i(t), P_i(t), M_i(t), B_i(t))$$

其中：
- $T_i(t)$ = 患者 $i$ 在时刻 $t$ 的转录组特征向量（维度 $d_T = 100-500$）
  - 核心基因集：IL-17A, IL-17F, RORγt, FOXP3, IL-10, TNF-α, IL-6等
  - 通常采用 log2-转换的基因表达量或PCA降维后的主成分

- $P_i(t)$ = 患者 $i$ 的蛋白质组向量（维度 $d_P = 12-46$）
  - 炎症蛋白：CRP, TNF-α, IL-6, IL-17A, IL-22
  - 纤维化标志物：periostin, LOX, TGF-β
  - 屏障蛋白：claudin-2, occludin, zonula occludens-1 (ZO-1)
  - 通常采用多重蛋白检测 (Luminex, Olink等)

- $M_i(t)$ = 患者 $i$ 的微生物组特征（维度 $d_M = 20-100$）
  - 关键指标：Shannon多样性 $H$, Simpson指数, 病原菌相对丰度
  - 功能基因：与SCFA产能相关的基因库
  - 通常采用宏基因组或16S rRNA基因序列

- $B_i(t)$ = 患者 $i$ 的代谢组向量（维度 $d_B = 50-200$）
  - SCFA（乙酸、丙酸、丁酸）浓度
  - 次级胆酸水平
  - 色氨酸代谢物（羌酸、吲哚衍生物）
  - 通常采用液相/气相质谱分析

### 1.2 数据预处理与标准化

```python
# 伪代码：Omic数据的标准化流程

def standardize_omic_data(raw_data_matrix: np.ndarray) -> np.ndarray:
    """
    输入: raw_data (n_samples × n_features)
    输出: standardized_data (相同维度，标准化)
    """
    # 步骤1：去除离群值 (99.5%分位数)
    Q995 = np.percentile(raw_data_matrix, 99.5, axis=0)
    cleaned_data = np.minimum(raw_data_matrix, Q995)
    
    # 步骤2：Log转换（对转录组和蛋白组）
    cleaned_data = np.log2(cleaned_data + 1)
    
    # 步骤3：样本级标准化 (Z-score)
    standardized = (cleaned_data - cleaned_data.mean(axis=0)) / cleaned_data.std(axis=0)
    
    # 步骤4：特征级归一化到 [0, 1]
    standardized = (standardized - standardized.min(axis=0)) / (standardized.max(axis=0) - standardized.min(axis=0))
    
    return standardized
```

### 1.3 基线多Omics表型的建立（周0）

```
患者诊断确认 → 多组学采样 → 标准化 → 基线特征向量 O_i(0)

关键质量指标：
  ✓ 转录组：>10M reads，覆盖度>1000X
  ✓ 蛋白：重复性CV<15%，检测范围内样品百分比>90%
  ✓ 微生物：>50K reads，Good's coverage >0.95
  ✓ 代谢：内标恢复率 80-120%，色谱分辨率 Rs>1.5
```

---

## II. 建模层：患者特异的预期轨迹构建

### 2.1 预期轨迹模型（Expected Trajectory Model）

**核心假设**：每个患者在启动治疗后，其Omic特征会沿着一条"缓解维持轨迹"演化，该轨迹由患者的基线特征、治疗方案和响应速度决定。

#### 2.1.1 参数化轨迹模型

对于维度 $d$ 的Omic特征，其预期轨迹可用**参数化曲线**表示：

$$\hat{O}_i^{(d)}(t; \theta_i^{(d)}) = O_i^{(d)}(0) + (O_{\text{target}}^{(d)} - O_i^{(d)}(0)) \cdot f(t; \theta_i^{(d)})$$

其中：
- $O_i^{(d)}(0)$ = 患者 $i$ 在维度 $d$ 的基线值
- $O_{\text{target}}^{(d)}$ = 健康参考值或缓解目标值
- $f(t; \theta_i^{(d)})$ = 患者特异的恢复函数，通常为S形曲线（Sigmoid或logistic）
- $\theta_i^{(d)}$ = 参数集合（中点时间、斜率、最大恢复速度）

#### 2.1.2 学习患者特异参数

```python
def fit_trajectory_model(omic_series: dict, dimension: str) -> dict:
    """
    使用患者的基线 + 周4数据拟合预期轨迹
    
    输入：
      omic_series: {'week0': array, 'week4': array, ...}
      dimension: 'transcriptome' | 'proteome' | 'microbiome' | 'metabolome'
    
    输出：
      trajectory_params: {'baseline': float, 'target': float, 
                         'midpoint': float, 'steepness': float}
    """
    from scipy.optimize import curve_fit
    
    # 获取观察数据
    time_points = np.array([0, 4])
    observed_values = np.array([omic_series['week0'], omic_series['week4']])
    
    # 定义logistic函数
    def logistic(t, baseline, target, midpoint, steepness):
        return baseline + (target - baseline) / (1 + np.exp(-steepness * (t - midpoint)))
    
    # 初始参数猜测
    baseline_guess = omic_series['week0']
    target_guess = omic_series['week4'] * 1.5  # 假设周4有30%改善
    midpoint_guess = 6  # 中点在周6附近
    steepness_guess = 0.5
    
    # 拟合
    try:
        popt, pcov = curve_fit(
            logistic,
            time_points,
            observed_values,
            p0=[baseline_guess, target_guess, midpoint_guess, steepness_guess],
            maxfev=5000,
            bounds=([baseline_guess*0.5, target_guess*0.1, 0, 0.01],
                    [baseline_guess*1.5, target_guess*2, 20, 2])
        )
        
        return {
            'baseline': float(popt[0]),
            'target': float(popt[1]),
            'midpoint': float(popt[2]),
            'steepness': float(popt[3]),
            'confidence': float(np.sqrt(np.diag(pcov)).mean())  # 平均置信度
        }
    except:
        return None  # 拟合失败
```

### 2.2 多维轨迹的联合模型

在实践中，四维轨迹需要**整体建模**而非独立：

```python
def build_multidimensional_trajectory(patient_id: str, omic_baseline: dict, 
                                     omic_week4: dict) -> dict:
    """
    为患者构建四维Omic轨迹的联合预期模型
    """
    dimensions = ['transcriptome', 'proteome', 'microbiome', 'metabolome']
    trajectory_model = {}
    
    for dim in dimensions:
        series = {
            'week0': omic_baseline[dim],
            'week4': omic_week4[dim]
        }
        
        params = fit_trajectory_model(series, dim)
        if params:
            trajectory_model[dim] = params
    
    # 维度间的共变性矩阵（用于联合分析）
    # 计算基线状态下，各维度之间的相关系数
    baseline_matrix = np.array([
        omic_baseline['transcriptome'],
        omic_baseline['proteome'],
        omic_baseline['microbiome'],
        omic_baseline['metabolome']
    ])
    
    covariance_matrix = np.corrcoef(baseline_matrix)
    trajectory_model['covariance'] = covariance_matrix
    
    return trajectory_model
```

---

## III. 监测层：实时轨迹对标与偏离检测

### 3.1 轨迹对标的核心算法

在每个监测时点 $t$（如周8、12、20等），计算患者**当前状态与预期轨迹的距离**：

#### 3.1.1 单维距离度量

对于维度 $d$，定义**标准化偏离指数（Normalized Deviation Index, NDI）**：

$$\text{NDI}_i^{(d)}(t) = \frac{|O_i^{(d)}(t) - \hat{O}_i^{(d)}(t)|}{\sigma_{\text{expected}}^{(d)}(t)}$$

其中：
- $O_i^{(d)}(t)$ = 患者实际观测值
- $\hat{O}_i^{(d)}(t)$ = 预期值（基于拟合的轨迹模型）
- $\sigma_{\text{expected}}^{(d)}(t)$ = 该维度在该时点的预期标准差（来自训练队列）

**解释**：
- NDI < 1：患者在预期轨迹范围内（正常）
- 1 ≤ NDI < 2：轻度偏离（预警）
- NDI ≥ 2：显著偏离（干预信号）

#### 3.1.2 多维复合偏离评分

```python
def calculate_multidimensional_deviation(
    patient_trajectory_model: dict,
    current_omic_measurement: dict,
    time_point: int
) -> dict:
    """
    计算患者在当前时点的多维偏离评分
    """
    dimensions = ['transcriptome', 'proteome', 'microbiome', 'metabolome']
    deviation_scores = {}
    
    # 步骤1：计算每个维度的单维NDI
    ndi_vector = []
    for dim in dimensions:
        params = patient_trajectory_model[dim]
        
        # 预期值
        expected = (params['baseline'] + 
                   (params['target'] - params['baseline']) / 
                   (1 + np.exp(-params['steepness'] * (time_point - params['midpoint']))))
        
        # 实际值
        actual = current_omic_measurement[dim]
        
        # 预期标准差（从训练集估计）
        sigma_expected = params.get('sigma', 0.1)  # 默认10%
        
        # 计算NDI
        ndi = abs(actual - expected) / sigma_expected
        ndi_vector.append(ndi)
        
        deviation_scores[f'ndi_{dim}'] = float(ndi)
    
    # 步骤2：计算综合偏离评分（考虑维度间相关性）
    ndi_vector = np.array(ndi_vector)
    cov_matrix = patient_trajectory_model['covariance']
    
    # 使用Mahalanobis距离加权
    try:
        cov_inv = np.linalg.inv(cov_matrix)
        mahal_distance = np.sqrt(ndi_vector.T @ cov_inv @ ndi_vector)
    except:
        # 如果矩阵奇异，使用简单平均
        mahal_distance = ndi_vector.mean()
    
    # 转换为0-100评分
    composite_score = min(100, (mahal_distance / 3.0) * 100)  # 3为参考阈值
    
    deviation_scores['composite_omic_score'] = float(composite_score)
    deviation_scores['alert_level'] = classify_alert_level(composite_score)
    
    return deviation_scores


def classify_alert_level(score: float) -> str:
    """根据偏离评分分类警告级别"""
    if score < 20:
        return "GREEN"  # 轨迹正常
    elif score < 50:
        return "YELLOW"  # 轻度偏离，预警
    elif score < 80:
        return "ORANGE"  # 中度偏离，需评估
    else:
        return "RED"  # 严重偏离，需干预
```

### 3.2 维度特异的偏离分析（Dimension-Specific Deviations）

```python
def analyze_dimension_specific_deviations(ndi_scores: dict) -> dict:
    """
    识别哪个维度（或维度组合）出现偏离
    用于针对性干预推荐
    """
    dimensions = ['transcriptome', 'proteome', 'microbiome', 'metabolome']
    dimension_ndi = {dim: ndi_scores[f'ndi_{dim}'] for dim in dimensions}
    
    # 排序：哪个维度偏离最大
    sorted_dims = sorted(dimension_ndi.items(), key=lambda x: x[1], reverse=True)
    
    # 生成诊断报告
    report = {}
    for i, (dim, ndi) in enumerate(sorted_dims, 1):
        if ndi < 1:
            status = "✓ 正常"
        elif ndi < 2:
            status = "⚠️ 轻度滞后"
        else:
            status = "🔴 显著偏离"
        
        report[f'rank_{i}'] = {
            'dimension': dim,
            'ndi': float(ndi),
            'status': status,
            'intervention_focus': recommend_intervention(dim, ndi)
        }
    
    return report


def recommend_intervention(dimension: str, ndi: float) -> str:
    """根据偏离维度推荐干预类型"""
    recommendations = {
        'transcriptome': {
            'threshold': 1.5,
            'action': "考虑增加或转换免疫生物制剂",
            'rationale': "转录组信号异常提示免疫控制不足"
        },
        'proteome': {
            'threshold': 2.0,
            'action': "评估是否存在隐匿感染或纤维化进展",
            'rationale': "蛋白质组滞后可能反映分子重构延迟或病理过程激活"
        },
        'microbiome': {
            'threshold': 1.5,
            'action': "启动微生物定向干预（FMT、益生菌、膳食纤维）",
            'rationale': "菌群失调恢复迟缓需要主动微生物重建"
        },
        'metabolome': {
            'threshold': 1.5,
            'action': "强化膳食纤维、补充短链脂肪酸或特定氨基酸",
            'rationale': "代谢恢复滞后提示肠道屏障和免疫恢复功能障碍"
        }
    }
    
    if ndi > recommendations[dimension]['threshold']:
        return recommendations[dimension]['action']
    else:
        return "继续观察，按计划评估"
```

---

## IV. 决策层：周期性决策树与干预触发

### 4.1 诱导期的三次关键决策点

#### **周4：早期反应轨迹识别**

```python
def decision_week4(patient_id: str, week0_omic: dict, week4_omic: dict) -> dict:
    """
    周4的三色决策：是否需要强化/转换？
    """
    
    # 构建预期轨迹（基于周0和周4）
    trajectory_model = build_multidimensional_trajectory(patient_id, week0_omic, week4_omic)
    
    # 评估临床改善（CDAI、FCP等）
    cdai_improvement = calculate_cdai_improvement()  # % 改善
    fcp_improvement = calculate_fcp_improvement()    # % 改善
    
    # 评估分子改善
    composite_omic_score = calculate_composite_omic_score(trajectory_model, week4_omic)
    
    # 决策逻辑
    if cdai_improvement > 50 and fcp_improvement > 50 and composite_omic_score < 30:
        decision = {
            'color': 'GREEN',
            'action': '继续当前治疗',
            'rationale': '快速反应者，预期周12达到CDC',
            'next_review': 'week8'
        }
    
    elif cdai_improvement > 30 and fcp_improvement > 30 and composite_omic_score < 50:
        decision = {
            'color': 'YELLOW',
            'action': '继续诱导，但加强周8评估',
            'rationale': '中等反应速度，需密切追踪',
            'next_review': 'week8 (强化监测)',
            'warning': '如周8无进展，考虑周8+强化'
        }
    
    else:  # cdai_improvement < 30 或 composite_omic_score > 50
        decision = {
            'color': 'RED',
            'action': '警告：延迟反应者，不建议等待周8',
            'rationale': '分子证据提示当前治疗效果不佳，需主动干预',
            'recommended_intervention': [
                '1. 评估依从性与药物吸收',
                '2. 考虑增加生物制剂剂量',
                '3. 考虑添加免疫抑制剂',
                '4. 周6进行强化前评估'
            ],
            'next_review': 'week6 (而非week8)'
        }
    
    return decision
```

#### **周8：中期治疗调整的关键窗口**

```python
def decision_week8(patient_id: str, trajectory_model: dict, 
                   week8_omic: dict, current_treatment: str) -> dict:
    """
    周8：强化 vs 转换 vs 继续的三层决策
    """
    
    # 监测当前轨迹
    week8_deviation = calculate_multidimensional_deviation(
        trajectory_model, week8_omic, time_point=8
    )
    
    composite_score = week8_deviation['composite_omic_score']
    alert_level = week8_deviation['alert_level']
    
    # 评估CDC进展（临床 + 内镜 + 组织学 + 炎症标志物 + PRO）
    cdc_progress = evaluate_cdc_progress()  # 0-5维的进展评分
    
    # 评估"时间陷阱"风险
    time_trap_risk = assess_time_trap_risk(
        weeks_of_insufficient_response=8,
        inflammatory_burden=composite_score,
        cdc_progress=cdc_progress
    )
    
    if composite_score < 30 and cdc_progress >= 4:
        # ✅ 绿灯：快速反应者
        decision = {
            'color': 'GREEN',
            'action': '继续当前治疗方案',
            'expected_cdc_achievement': 'week12',
            'next_milestone': 'week12评估CDC达成'
        }
    
    elif 30 <= composite_score < 60 and cdc_progress >= 3:
        # 🟡 黄灯：延迟反应者，需强化
        dimension_issues = analyze_dimension_specific_deviations(week8_deviation)
        
        decision = {
            'color': 'YELLOW',
            'action': '强化治疗',
            'methods': {
                'option1': f'增加{current_treatment}剂量 (建议:增加25-50%)',
                'option2': '添加互补机制的生物制剂（如TNF→IL-23）',
                'option3': '添加免疫抑制剂（硫唑嘌呤、巯基嘌呤）',
                'targeted_intervention': dimension_issues
            },
            'rationale': '延迟反应但有进展，强化可能在周12前达到CDC',
            'reassessment_timeline': 'week10-11 (而非week12)',
            'time_trap_warning': f'时间陷阱风险评分: {time_trap_risk}/100'
        }
    
    else:
        # 🔴 红灯：非反应者或快速复发，转换MOA
        decision = {
            'color': 'RED',
            'action': '转换治疗（不同MOA）',
            'recommendation': recommend_moa_switch(week8_omic, current_treatment),
            'rationale': '分子证据明确提示当前MOA无效，继续延迟会导致不可逆损伤',
            'suggested_switch': {
                'if_current_is_tnf': '→ IL-23抑制剂 或 整合素抑制剂',
                'if_current_is_il23': '→ TNF抑制剂 或 JAK抑制剂',
                'baseline_repeat': '建议周8+重复多组学，确认MOA特异的失效机制'
            },
            'time_trap_urgency': f'时间陷阱风险: {time_trap_risk}/100 (>70为紧急)'
        }
    
    return decision
```

#### **周12：缓解达成评估**

```python
def decision_week12(patient_id: str, trajectory_model: dict, 
                    week12_omic: dict) -> dict:
    """
    周12：CDC达成 ∩ Omic缓解的双标准评估
    """
    
    # 评估CDC五维标准
    cdc_status = evaluate_comprehensive_disease_control(week12_omic)
    cdc_achieved = cdc_status['achieved']  # True/False
    
    # 评估Omic缓解
    omic_remission = evaluate_omic_remission(trajectory_model, week12_omic)
    omic_complete = omic_remission['complete']  # True/False
    
    # 分层结果
    if cdc_achieved and omic_complete:
        # ✅ 结果A：完全缓解
        outcome = {
            'category': 'A: 完全缓解',
            'cdc_status': '✅ 达成',
            'omic_status': '✅ 深度正常化',
            'enrollment_pathway': '标准维持（PHASE 3）',
            'maintenance_plan': {
                'biologic_frequency': '继续原治疗，不减量',
                'monitoring_frequency': 'FCP + CRP 每月',
                'deep_omics_frequency': '每3个月重评转录组',
                'mrd_surveillance': '每2周液体活检'
            },
            'expected_1year_relapse_risk': '<10%',
            'note': '患者可进入长期缓解维持，预期可评估停药（3-5年缓解后）'
        }
    
    elif cdc_achieved and not omic_complete:
        # ⚠️ 结果B：临床缓解但Omic不完全
        incomplete_dimensions = identify_incomplete_omic_dimensions(week12_omic, trajectory_model)
        
        outcome = {
            'category': 'B: 临床缓解，Omic不完全',
            'cdc_status': '✅ 达成',
            'omic_status': f'⚠️ 不完全 (维度: {incomplete_dimensions})',
            'enrollment_pathway': '强化维持（PHASE 3 Plus）',
            'maintenance_plan': {
                'biologic_strategy': '维持当前生物制剂，不减量',
                'additional_intervention': f'针对{incomplete_dimensions}的定向干预',
                'monitoring_frequency': 'FCP + CRP 每2周',
                'deep_omics_frequency': '每2周液体活检 + 每1-2月转录组',
                'dietary_intervention': '根据不完全维度推荐'
            },
            'expected_1year_relapse_risk': '15-20%',
            'rationale': f'{incomplete_dimensions}维度未完全恢复提示潜在风险',
            'next_milestone': 'week16评估强化是否起效'
        }
    
    else:
        # ❌ 结果C：CDC未达成
        outcome = {
            'category': 'C: CDC未达成',
            'cdc_status': '❌ 未达成',
            'omic_status': '❌ 未改善或恶化',
            'status': '诱导期治疗失败',
            'next_action': '调整方案，重新治疗',
            'options': [
                '1. 增加当前生物制剂剂量',
                '2. 切换至不同MOA',
                '3. 开始联合治疗（生物制剂 + 免疫抑制剂）'
            ],
            'reassessment_timeline': 'week16-20',
            'duration_extension': '诱导期延长至16-20周'
        }
    
    return outcome
```

---

## V. 维持期的MRD驱动决策

### 5.1 MRD阈值与预防性强化触发

```python
def evaluate_mrd_and_trigger_intervention(
    patient_id: str,
    maintenance_week: int,
    mrd_measurements: dict,
    baseline_trajectory: dict
) -> dict:
    """
    维持期每4周评估：MRD升高是否需要强化？
    """
    
    # 获取当前MRD指标
    fcp_current = mrd_measurements['fcp']  # μg/g
    fcp_baseline = mrd_measurements['fcp_at_week12']
    
    protein_score = mrd_measurements['composite_protein_score']  # 0-1标准化
    transcript_score = mrd_measurements.get('omic_risk_score', None)  # AI评分
    
    # 规则1：FCP异常
    rule1_triggered = False
    if (fcp_current < 100) and (fcp_current > fcp_baseline + 100):
        # 从<100升至>200
        rule1_triggered = True
        rule1_evidence = f"FCP {fcp_baseline:.0f} → {fcp_current:.0f}"
    elif fcp_current > 150 for two_consecutive_weeks:
        # 连续2周>150
        rule1_triggered = True
        rule1_evidence = "连续2周 FCP >150"
    
    # 规则2：转录组/蛋白异常
    rule2_triggered = False
    if protein_score > 0.5 or transcript_score > 0.6:
        rule2_triggered = True
        rule2_evidence = f"Protein score {protein_score:.2f} | Transcript {transcript_score:.2f}"
    
    # 规则3：临床症状（通常最后出现）
    rule3_triggered = patient_reports_symptom_increase()
    
    # 触发决策
    if rule1_triggered and rule2_triggered:
        # ✅ 双规则触发：立即强化（不等症状）
        action = {
            'trigger': 'RULES_1_2',
            'action': '立即启动预防性强化',
            'timing': '本周启动',
            'evidence': [rule1_evidence, rule2_evidence],
            'urgency': 'HIGH',
            'strength': '分子证据强，提示亚临床复发'
        }
    
    elif rule1_triggered or rule2_triggered:
        # ⚠️ 单规则触发：加强监测，准备强化
        action = {
            'trigger': 'RULE_1_OR_2',
            'action': '加强监测频率 (周而非隔周)',
            'timing': '如果下周确认，启动强化',
            'evidence': [rule1_evidence if rule1_triggered else rule2_evidence],
            'urgency': 'MEDIUM'
        }
    
    elif rule3_triggered:
        # 🔴 仅临床症状：已太迟
        action = {
            'trigger': 'RULE_3_ONLY',
            'action': '患者已进入临床复发，紧急启动强化',
            'timing': '立即',
            'evidence': ['患者症状明显增加'],
            'urgency': 'CRITICAL',
            'note': '预防性预警失败，已进入临床复发阶段'
        }
    
    else:
        action = {
            'trigger': 'NONE',
            'action': '继续维持，按计划评估',
            'next_mrd_assessment': f'week{maintenance_week + 4}'
        }
    
    return action
```

---

## VI. 实施流程与关键指标

### 6.1 完整的周期性监测流程

```
患者诊断
  ↓
【周0】多组学基线采样 + 初始治疗选择
  ↓
【周4】临床 + 部分Omics评估 + AI轨迹预测
  ├→ 快速反应：继续
  ├→ 延迟反应：强化前评估
  └→ 非反应：考虑周6-8强化
  ↓
【周8】中期多组学重评 + 三色决策
  ├→ 绿灯：继续诱导
  ├→ 黄灯：强化执行
  └→ 红灯：MOA转换
  ↓
【周12】完整CDC + Omic缓解评估
  ├→ 完全缓解：进标准维持
  ├→ 临床缓解/Omic不完全：强化维持
  └→ CDC未达：延长诱导期
  ↓
【维持期 周12-52】MRD驱动的预防强化
  ├→ 规则1+2触发：立即强化
  ├→ 规则1或2触发：加强监测
  └→ 无触发：标准维持
  ↓
【长期 年1+】停药可能性评估
```

### 6.2 关键性能指标（KPIs）

| KPI | 目标值 | 说明 |
|-----|--------|------|
| **周12 CDC达成率** | >70% | 四阶段框架有效性的主要指标 |
| **周12 Omic缓解率** | >50% | 深度生物正常化的达成 |
| **1年复发率（CDC+Omic）** | <10% | 完全缓解组的预后 |
| **MRD预警的早期性** | 4-6周提前 | 在临床症状前识别复发信号 |
| **AI轨迹预测准确率** | >80% | P(CDC达成 \| AI预测)的校准度 |
| **维度特异干预的有效率** | >60% | dysbiosis特异的FMT等干预成功率 |

---

## 关联连接

### 核心概念
- [[OmicTrajectory]] — 纵向轨迹医学的定义与临床意义
- [[OmicPhenotype]] — 多维Omic表型的建立
- [[ComprehensiveDiseaseControl]] — 五维缓解标准
- [[MinimalResidualDisease_IBD]] — 维持期MRD监测

### 临床应用
- [[synthesis-ibd-omics-intelligence-loop]] — 完整的四阶段闭环框架
- [[PatientAsSensor-Technical-Stack]] — 多源数据融合的技术实施
- [[TherapeuticResponseTrajectory]] — 患者反应轨迹的分类与预后

### 工具与支撑
- [[AIasClinicalPartner]] — AI决策支持系统的架构
- [[TDM_Guided_Dietary_Integration]] — 治疗监测与膳食协同

---

**最后更新**：2026-04-29  
**版本**：1.0 - 完整的轨迹医学实施指南  
**适用对象**：临床医学信息学、精准医学AI研发、IBD治疗决策支持系统开发