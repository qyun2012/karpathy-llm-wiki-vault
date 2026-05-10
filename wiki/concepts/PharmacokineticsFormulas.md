---
title: "Pharmacokinetics Formulas and Parameters"
type: concept
tags: [药代动力学, PK, 清除率, 生物利用度, 数学模型]
sources: [raw/02-papers/Clinical Gastroenterology and Hepatology 2025_PK.pdf, raw/02-papers/Early Infliximab Levels and Clearance Predict Outcomes After Infliximab Rescue in ASUC.pdf]
last_updated: 2026-04-26
---

# 药代动力学计算公式汇总

## 一、两室模型（Two-Compartment Model）

### 1. 体积分布计算

#### 中心室体积 (Vt)
```
Vt = 3.29 × (weight_kg / 77)^0.86
```
**说明**：
- 基于体重的缩放公式
- 用于归一化不同患者体重的差异
- 指数0.86为异速生长指数 (allometric exponent)

#### 周边室体积 (Vz)
```
Vz = 4.13 × 0.3166 (个体清除率)
```
**说明**：
- 周边分布体积与个体清除率相关
- 反映药物在周边组织中的分布

#### 总体积分布 (Vd)
```
Vd = Vt + Vz
```

---

### 2. 清除率（Clearance）计算

#### 估计日清除率 (Estimated Daily Clearance)
根据血清浓度在不同时间点的变化：

```
CL_day3 = 通过Day 1和Day 3血清浓度估计
CL_day7 = 通过Day 3和Day 7血清浓度估计
CL_day30 = 通过Day 7和Day 30血清浓度估计
CL_day90 = 通过Day 30和Day 90血清浓度估计
```

#### 房室间清除率 (Inter-compartmental Clearance)
```
q = 中心室与周边室之间的药物流速参数
```

---

### 3. 清除率与临床结果的关联

#### Day 3血清浓度预测Day 14失败
| 指标 | 值 | 临床意义 |
|------|-----|--------|
| Area Under Curve (AUC) | 0.63 | Day 3血清IFX浓度：Day 14 IFX失败的敏感性83.3%，特异性67%，PPV 24%，NPV 96% |
| 临界值 | ≤57.9 μg/mL | 低浓度预测更高的失败风险 |

#### Day 3粪便浓度预测结局
```
粪便IFX浓度 ≤ 1.4 μg/mL → Day 7非反应者更多
粪便IFX浓度升高 → 与肠道病变严重程度相关
```

---

### 4. 最大似然估计（Maximum Likelihood Estimation）

```
参数估计方法：使用MLE假设对数正态分布
- 给定未检测浓度下限值（<2 μg/mL）
- 进行非参数英夫利昔单抗浓度估计
```

---

## 二、贝叶斯预测模型（Bayesian Forecasting）

### 应用于群体药代动力学 (popPK Model)

#### 基本原理
```
使用测量的血药浓度 + 房室外PK模型 + 个体参数
↓
预测特定患者的给药方案最优化
```

#### 计算步骤
1. **收集数据**：血清和粪便样本（w4, w8, w16, w24等时间点）
2. **建立模型**：nonmem模型（版本7.5+），popPK包
3. **参数估计**：基于个体的清除率（CL）和浓度分布
4. **预测**：使用maphyr包进行贝叶斯预测

---

## 三、目标浓度（Target Trough Concentration, Ctrough）

### 不同治疗阶段的目标值

| 治疗阶段 | Ctrough目标 | 清除率(CL)目标 | 临床应用 |
|---------|-----------|-------------|--------|
| **诱导期** | ≥5 mg/L | - | 初始给药优化 |
| **维持期** | 3-7 mg/L | **0.22 L/day** | 优化肠内视镜缓解 |
| **普通TDM策略** | 5 mg/L | - | 基于浓度调整剂量 |
| **强化方案** | 3-10 mg/L | - | 针对高清除率患者 |

### 与临床转归的关系

```
Ctrough < 3 mg/L → 高复发风险
Ctrough ≥ 5 mg/L ∩ CL低 → 更好的肠内视镜缓解
```

---

## 四、受试者操作特征（ROC）分析

### 用于评估预测指标的判别力

```
AUROC = 曲线下面积（0-1之间）

预测指标判别力排序（高→低）：
1. Infliximab Clearance (AUROC: 0.70-0.72)
2. Ctrough (AUROC: 0.64-0.67)
3. CRP / 粪便钙蛋白 (AUROC: 0.50-0.60)

关键阈值：
- Infliximab CL ≤ 0.26 L/day → 肠内视镜缓解风险增加
- 灵敏度: 59-71%，特异性: 62-78%，PPV: 42-88%，NPV: 34-89%
```

---

## 五、参数相关性分析

### Day 3清除率影响因素

| 影响因素 | 相关系数 (ρ) | P值 | 临床意义 |
|---------|-----------|-----|--------|
| Day 0 CRP | 0.43 | <0.001 | 高炎症 → 高清除率 |
| 体重 | 0.44 | <0.001 | 体重增加 → 清除率增加 |
| 白细胞计数 | - | 0.30 | 免疫激活程度 |
| 血清白蛋白 | -0.27 | 0.020 | 营养状况 |

### 清除率动态变化

```
Day 1-3: 最高清除率（中值: 0.49 L/d，IQR: 0.41-0.76）
Day 3-7: 清除率下降（平均下降 -29.3%，范围 -45.1% to -9.9%）
Day 7-30: 继续下降（平均下降 -17.4%，IQR: -24.1% to -1.5%）
Day 30-90: 趋于稳定（中值差异不显著）
```

---

## 六、关键统计指标

### 灵敏度与特异性

#### Day 3血清IFX水平预测Day 14失败（初始5mg/kg）
```
阈值: ≤57.9 μg/mL
灵敏度 (Sensitivity): 83.3%
特异性 (Specificity): 67%
正预测值 (PPV): 24%
负预测值 (NPV): 96%
```

#### Day 3粪便IFX水平预测肠镜缓解
```
阈值: ≤2.1 μg/mL
灵敏度: 67.4%
特异性: 68.8%
PPV: 42.3%
NPV: 87.1%
```

---

## 七、Youden Index确定最优阈值

```
Youden Index (J) = 灵敏度 + 特异性 - 1

最大化 J 值 → 确定最优的临床决策阈值

例：Day 3血清IFX ≤57.9 μg/mL 时 J 最大
  → 该阈值最优地区分Day 14失败风险
```

---

## 八、非参数方法：AUROC计算

```
应用于：
- 诱导期预测 (w2 vs w12 endoscopic remission)
- 维持期预测 (w54 endoscopic remission)
- 药物浓度 vs 清除率的预测力比较

输出：
- ROC曲线（绘制灵敏度 vs 1-特异性）
- AUROC值（0.5-1.0）
- 95% 置信区间 (CI)
- 最优阈值及对应的性能指标
```

---

## 九、多变量Poisson回归

用于识别Day 14英夫利昔单抗失败的独立预测因素：

```
独立预测因素：
1. 早期清除率升高 (RR: 3.96 per L/d, 95% CI: 1.83-8.58, P = 0.0005)
2. Lichtiger评分高 (RR: 1.08 per point, 95% CI: 1.03-1.14, P = 0.0038)
3. 基线硫唑嘌呤使用 (RR: 0.54, 95% CI: 0.35-0.82, P = 0.0043)

非独立因素：
- 初始英夫利昔单抗剂量
- Day 0白细胞计数
```

---

## 十、群体药代动力学(popPK)模型参数

### 模型类型：2房室模型

```
参数集合：
- CL (中心清除率，L/d)
- Vc (中心分布体积，L)
- Q (房室间清除率，L/d) 
- Vp (周边分布体积，L)
- Ka (吸收速率常数，对IV给药 = 0)

变异性模型：
- IIV (个体间变异性)：体重缩放指数 0.75-0.86
- RUV (残留变异性)：加法或乘法模型
```

---

## 十一、临床转化指标

### 用于TDM(治疗药物监测)决策

#### 推荐决策框架

| 临床状态 | Ctrough | CL | 推荐方案 |
|---------|---------|-----|--------|
| 无临床/生化缓解 | <5 mg/L | 高 | 反应式剂量升级 |
| 临床缓解 | ≥5 mg/L | 低 | 不需调整 |
| 生化缓解 | ≥5 mg/L | 低 | 考虑停药 |
| 高清除率风险 | - | >0.26 L/day | 预防性剂量升级 |

---

## 十二、数据来源说明

### 论文一：PREDICT-UC试验
- **发表期刊**：Gastroenterology 2026; 170:118-131
- **样本量**：135名患者（681份血清，198份粪便样本）
- **关键发现**：Day 3血清/粪便IFX浓度与预后关联；高清除率可通过增加剂量克服

### 论文二：TAILORIX & Leuven ustekinumab试验
- **发表期刊**：Clinical Gastroenterology and Hepatology 2025
- **样本量**：Infliximab 108例，Ustekinumab 80例
- **关键发现**：清除率(CL)比Ctrough更好地预测肠镜缓解

---

## 关联连接

- [[InfliximabTherapy]]
- [[TherapeuticDrugMonitoring]]
- [[AcuteSevereUlcerativeColitis]]
- [[IBDTreatmentOutcomes]]
- [[CrohnsDiseaseManagement]]

