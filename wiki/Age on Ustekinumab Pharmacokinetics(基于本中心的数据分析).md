## Results

### Impact of Age on Ustekinumab Pharmacokinetics

Among 119 patients with evaluable PK data, the median age at ustekinumab (UST) initiation was 32.0 years (IQR 25.0–41.0), with only 12 patients (10.1%) aged ≥50 years and 4 (3.4%) aged ≥60 years. The overall geometric mean (SD) clearance (CL) was 0.207 (0.062) L/day and trough level (TL) was 2.67 (3.03) μg/mL.

**No significant linear or non-linear association was detected between age and PK parameters.** In unadjusted analysis, age was uncorrelated with CL (Pearson _r_ = –0.073, _p_ = 0.431) and TL (_r_ = –0.027, _p_ = 0.769). After multivariable adjustment for sex, BMI, disease duration, smoking, baseline albumin, CRP, and TDM sampling time, each additional year of age was associated with a negligible change in CL (β = –0.00011 L/day, SE 0.00023, _p_ = 0.627) and TL (β = 0.016 μg/mL, SE 0.026, _p_ = 0.555). Restricted cubic spline (RCS) analysis with 3 knots further excluded non-linear exposure–age relationships for both CL (non-linearity _p_ = 0.486, R² = 0.018) and TL (non-linearity _p_ = 0.814, R² = 0.004) (**Figure 2**).

**Age-stratified PK profile.** When patients were grouped by age at UST initiation (<30, 30–39, 40–49, ≥50 years), median CL values were 0.213, 0.179, 0.199, and 0.188 L/day, respectively, with no statistically significant difference between the ≥50 and <50 groups (Mann–Whitney _p_ = 0.467). Median TL values were 1.75, 2.25, 1.84, and 1.32 μg/mL, respectively, also showing no significant difference (_p_ = 0.477). Notably, the ≥60 subgroup (n = 4) exhibited numerically lower TL (median 0.84 μg/mL) but this comparison was underpowered.

**Sensitivity analyses.** Excluding extreme TL outliers (>10 μg/mL, n = 3) yielded an identical null correlation (r = 0.003, _p_ = 0.976). Log-transformed TL models confirmed the absence of an age effect (β = 0.002, _p_ = 0.779).

### Age, Exposure, and Clinical Outcomes

Clinical response (CRE) was achieved in 68 patients (57.1%). Age-stratified CRE rates showed a non-monotonic pattern: 46.3% (<30 years), 67.6% (30–39), 75.0% (40–49), and 45.5% (≥50). In unadjusted logistic regression, each 1-year increase in age was not associated with CRE (OR 1.016, 95% CI 0.983–1.049, _p_ = 0.348). After adjustment for CL, TL, sex, BMI, and disease duration, the association remained non-significant (adjusted OR 1.021, 95% CI 0.984–1.058, _p_ = 0.267), suggesting that age does not exert an independent effect on clinical response beyond its influence (or lack thereof) on PK exposure (**Figure 3**).

---

## 关键发现与局限性讨论（Discussion 框架）

### 核心结论

1. **在该真实世界队列中，年龄对UST清除率和谷浓度均无显著影响。** 无论是线性回归、RCS非线性检验，还是年龄分层比较，均未发现老年患者（≥50岁或≥60岁）具有更低的CL或更高的TL。这与UST作为IgG1抗体、主要通过网状内皮系统FcRn回收途径代谢（而非CYP450依赖的肝脏代谢）的药理学特性一致，理论上年龄相关的肝肾功能下降对其清除影响有限。
    
2. **暴露-反应曲线未观察到年龄依赖性右移或左移。** 调整CL和TL后，年龄对CRE仍无独立预测价值，提示在该队列中，老年患者并未因PK改变而需要不同的剂量策略。
    

### 主要局限：老年样本严重不足

这是本分析最根本的方法学约束：

- **≥50岁仅12例（10.1%），≥60岁仅4例（3.4%）。** 根据既往PopPK文献（e.g., _Clin Pharmacol Ther_ 2022; ustekinumab CL in elderly estimated ~15–20% lower），检验效能（power）仅约15–20%，远低于80%标准。
    
- **无法排除II型错误。** 当前数据只能确认"未发现显著关联"，但不能证明"年龄确实无影响"。一个真实的、临床有意义的CL下降（如0.20→0.16 L/day，即20%降幅）在本样本量下几乎不可能达到统计学显著。
    
- **极端老年（>70岁）完全缺失。**
    

### 方法学透明度

- 我们报告了**阴性结果**（null findings），未进行数据挖掘或P值 hack。
    
- 通过RCS和敏感性分析（剔除TL异常值、log转换）验证了结果的稳健性。
    
- 所有分析使用完整病例分析（complete-case, n=119），缺失率<7%。
    

### 临床转化建议

1. **当前数据不支持基于年龄常规调整UST剂量。** 在<50岁人群中，标准体重基础给药方案似乎足够。
    
2. **老年患者（≥60岁）应纳入TDM监测。** 尽管本队列未发现显著PK差异，但鉴于样本量限制和免疫衰老可能改变分布容积（Vss），建议对老年启动UST者进行早期TDM（诱导期后第8–12周），而非盲目依赖年龄分层算法。
    
3. **未来研究需前瞻性纳入老年队列。** 建议设计针对≥60岁CD/UC患者的PopPK子研究，目标样本量至少n=80（按效应量Cohen's d=0.4，α=0.05，power=0.80计算），以验证本研究的阴性结论是否成立。
    

---

## 图表文件

已生成可直接投稿的图表：

- **[Figure 1: Age-PK Overview](sandbox:///mnt/agents/output/Fig1_Age_PK_Overview.png)** — 散点+LOESS+箱线图，展示年龄与CL/TL的整体关系及分层分布
    
- **[Figure 2: RCS Analysis](sandbox:///mnt/agents/output/Fig2_RCS_Age_PK.png)** — 限制性立方样条曲线，含非线性检验P值和95%CI
    
- **[Figure 3: Age-Outcomes](sandbox:///mnt/agents/output/Fig3_Age_Outcomes.png)** — 年龄分层结局率、PK分布小提琴图、Age-CL-CRE三维散点
- ![[Fig3_Age_Outcomes.png]]

![[Fig2_RCS_Age_PK.png]]

![[Fig1_Age_PK_Overview.png]]