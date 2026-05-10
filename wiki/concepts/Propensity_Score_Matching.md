---
title: "Propensity Score Matching (PSM)"
type: concept
tags: [统计方法, 因果推断, 观察性研究, 混杂控制, 流行病学]
sources: ["Clippings/Association Between Ultraprocessed Food Intake and Inflammatory Bowel Disease Risk A Propensity-Matched Analysis With Monte Carlo Simulation From the Prospective Urban Rural Epidemiology Study.md"]
last_updated: 2026-05-08
---

## 定义与理论基础

**倾向评分（Propensity Score）定义**：
给定观察到的协变量X，接受某一治疗或暴露的概率。数学表示为：
$$PS = P(E=1|X)$$
其中E为暴露状态（1=暴露，0=未暴露），X为所有观察到的协变量。

**倾向评分匹配（PSM）原理**：
基于Rosenbaum和Rubin的选择偏倚理论，如果满足"条件独立假设"（在给定倾向评分条件下，暴露与混杂变量独立），PSM可将观察性研究转化为类似随机对照试验（RCT）的因果推断。

## PSM的统计步骤

### 第1步：倾向评分模型建立

**逻辑回归模型**：
$$\log\frac{PS}{1-PS} = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + ... + \beta_k X_k$$

**UPF-IBD研究中的协变量（混杂因素）**：
- 年龄、性别
- 城市vs乡村居住地
- 教育程度
- 体重指数（BMI）
- 吸烟状态
- 日能量摄入
- 膳食质量（替代健康饮食指数，AHEI）

**模型诊断**：
- 检验倾向评分分布的重叠（common support）
- 确保暴露组和对照组有可比的倾向评分范围

### 第2步：匹配算法选择

**一对一（1:1）匹配**：
- 对于每个暴露个体，从对照组中选择倾向评分最接近的个体
- UPF研究采用：分层匹配（UPF摄入不同水平分别匹配）

**配对方式**：
- **最近邻法**：选择PS差值最小的对照
- **卡尺方法**（Caliper）：仅匹配PS差值<某阈值的个体（通常<0.25×标准差）
- 减少偏倚但可能减少样本量

**结果**（UPF研究）：
- 13,970名倾向评分匹配的参与者
- 原始样本：110,600名（非西方）+ 14,898名（西方）
- 保留率：~94%（西方）

### 第3步：匹配前后平衡检验

**标准化差分（Standardized Difference）**：
$$d = \frac{\overline{X}_{exposed} - \overline{X}_{unexposed}}{\sqrt{(SD_{exposed}^2 + SD_{unexposed}^2)/2}}$$

**解释**：
- |d| < 0.1：良好平衡
- |d| 0.1-0.2：可接受
- |d| > 0.2：不平衡，需要调整

**平衡性验证**：
- 匹配前：多个协变量可能存在显著不平衡（|d|>0.2）
- 匹配后：所有协变量|d|<0.1（达到RCT水平）

## 因果参数估计

### 方法1：配对差分法（Paired Difference）

**对于离散结局**（如IBD发生）：
$$\text{Risk Ratio} = \frac{Risk_{exposed}}{Risk_{unexposed}}$$

**UPF研究结果**：
- 风险比（RR）0.53（95% CI, 0.51-0.55）
- 解释：低UPF摄入者IBD风险为常规饮食的53%

### 方法2：回归调整

**条件逻辑回归**（matched pairs）：
虽然PSM已平衡协变量，但仍可在匹配样本中进行回归，估计调整后风险比。

**UPF研究**：
- 调整后风险比（aHR）0.56（95% CI, 0.54-0.58）
- 额外调整可能的残留混杂

## PSM的优点

1. **易于理解与解释**：倾向评分是单一值，便于解释
2. **可视化**：倾向评分分布可图形展示平衡性
3. **灵活性**：可结合其他因果推断方法（如DID、工具变量）
4. **现实应用**：广泛应用于流行病学、医学、社会科学

## PSM的局限与批评

### 理论限制

**1. 隐性混杂（Unmeasured Confounding）**：
- PSM仅控制**观察到的**协变量
- 若存在**未测量或无法测量**的混杂因素，因果推断失效
- **UPF研究中的例子**：
  - 种族/民族背景（论文明确提及为限制）
  - 遗传易感性
  - 某些生活方式因素

**敏感性分析**：
Rosenbaum提出方法评估隐性混杂的影响大小（Γ：假设隐性混杂改变风险比的因子）。

**2. 条件独立假设（CIA）的不可验证性**：
- PSM无法直接验证CIA是否满足
- 需要理论论证该假设合理性
- 通常需要领域专业知识

### 统计限制

**3. 样本量损失**：
- 匹配过程可能排除无法匹配的个体
- 降低统计效力和外推性
- **UPF研究**：保留13,970/14,898 = 93.8%（西方）

**4. 完美多重共线性**：
- 若倾向评分完美预测暴露（完全分离），匹配无法进行
- 需要common support假设

**5. 过度匹配问题**：
- 在某些情况下，过度匹配（控制太多变量）可能增加偏倚
- "Plate collider bias"：若匹配变量受暴露和结局共同影响，可引入偏倚

### 实践限制

**6. 匹配后未完全消除混杂**：
- 即使平衡性良好，残留混杂仍可能存在
- 特别是在样本量小或协变量多时

**7. 参数灵活性**：
- 卡尺大小、匹配比例等选择主观
- 可导致不同研究相同数据得出不同结论

## PSM与替代方法的比较

| 方法 | 优点 | 缺点 | 适用场景 |
|------|------|------|--------|
| **PSM** | 易理解，易可视化 | 样本损失，CIA不可验证 | 中等样本，多个混杂因素 |
| **反向概率加权（IPW）** | 全样本利用，更有效 | 极端权重可能不稳定 | 大样本，稀有暴露 |
| **分层（Stratification）** | 简单，可视化 | 维度灾难（多变量时困难） | 少量离散混杂 |
| **回归调整** | 直接，参数少 | 可能漏掉非线性 | 混杂因素少 |
| **机器学习平衡** | 自动变量选择 | 黑箱，可重复性差 | 高维数据 |

## 在IBD研究中的应用示例

### UPF-IBD研究的PSM应用

**步骤1：倾向评分建立**
- 逻辑回归：UPF摄入 ~ 年龄 + 性别 + 城市/乡村 + 教育 + BMI + 吸烟 + 能量摄入 + AHEI

**步骤2：分层匹配**
- UPF <1份/天 vs ≥1份/天
- 按倾向评分1:1邻近邻匹配（卡尺<0.25×SD）
- 西方队列中配对13,970人

**步骤3：平衡检验**
- 匹配前/后标准化差分对比
- 所有协变量匹配后|d|<0.1

**步骤4：因果估计**
- 配对Cox回归：调整后风险比（aHR）0.56

**步骤5：灵敏性分析**
- 按随访时间分层：早期（5年）vs 晚期（15-20年）
- 结果一致：保护性关联增强（aHR 0.62→0.30）

## 实际建议与最佳实践

### 报告标准（STROBE-PSM）

PSM研究应报告：
1. ✅ 倾向评分模型的所有协变量
2. ✅ 匹配前后的平衡统计量
3. ✅ 样本流程图（原始→匹配→分析）
4. ✅ 倾向评分分布（overlap检查）
5. ✅ 灵敏性分析（隐性混杂评估）
6. ✅ 置信区间和p值

### 改进与扩展

**1. 联合方法**：
- PSM + 回归调整（双稳健估计）
- PSM + 倾向评分分层
- PSM + 工具变量法

**2. 动态处理与G-估计**：
- 对于时变暴露或处理顺序问题
- 参数化g-公式（如PURE研究使用）

**3. 机器学习增强**：
- 使用随机森林估计倾向评分
- 自动协变量选择
- 但需谨慎模型解释性

## 关联连接

- [[IBD]] — 炎症性肠病
- [[Ultraprocessed_Food]] — 超加工食品与IBD风险
- [[因果推断与观察性研究]] — 观察性数据的因果推断方法论（如存在）
- [[混杂因素控制]] — 混杂偏倚的定义与控制
- [[摘要-upf-ibd-propensity-matched-analysis]] — PURE研究应用示例

---

## 参考文献

1. Rosenbaum PR, Rubin DB. The central role of the propensity score in observational studies for causal effects. *Biometrika*. 1983;70(1):41-55.

2. Austin PC. An introduction to propensity score methods for reducing the effects of confounding. *Multivariate Behavioral Research*. 2011;46(3):399-424.

3. Narula N, Wong ECL, Rangarajan S, et al. Association between ultraprocessed food intake and inflammatory bowel disease risk: A propensity-matched analysis with Monte Carlo simulation from the Prospective Urban Rural Epidemiology Study. *Gastroenterology*. 2025;168(6).

