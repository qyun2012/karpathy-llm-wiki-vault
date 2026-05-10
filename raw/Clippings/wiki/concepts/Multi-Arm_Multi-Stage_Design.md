---
title: "Multi-Arm Multi-Stage Design"
type: concept
tags: [临床试验方法学, 生物统计学, 试验设计]
sources: [raw/Clippings/Developing an adaptive platform trial for evaluation of medical treatments for Crohn's disease - Nature Reviews Gastroenterology & Hepatology.md]
last_updated: 2026-05-04
---

## 定义

多臂多阶段设计（Multi-Arm Multi-Stage, MAMS）是一种统计和实验设计框架，允许一项临床试验在多个中期分析时间点同时比较三个或以上的干预臂，并根据累积的证据动态调整试验进行。它是现代自适应平台试验的数学基础。

## 核心统计原理

### 1. 多臂架构
```
         Interim Analysis 1       Interim Analysis 2       Final Analysis
                |                        |                       |
         ┌─────────────┐           ┌────────────┐         ┌──────────────┐
    Arm 1├─────────────┤───┬───┬───┤  STOP      ├─────────┤EFFICACY      │
    Arm 2├─────────────┤───┼───┼───┤  (futility)├─────────┤CONFIRMED     │
    Arm 3├─────────────┤───┼───┼───┤  / DROP    ├─────────┤(p<0.025)     │
    Arm 4├─────────────┤───┤   │   └────────────┘         └──────────────┘
    Ctrl ├─────────────┤───┘   │
         └─────────────┘       └─ ADD NEW ARM if warranted
              n=100          (n=100 cum)        (n=200 cum)
```

### 2. 多阶段分析
- **预设的中期分析**：试验进行至特定patient numbers或follow-up时间点进行分析
- **无效性停止规则（Futility Stopping）**：若某臂显示无效，立即停止该臂招募
- **有效性停止规则（Efficacy Stopping）**：若某臂显示明确有效，可提前宣布成功
- **第一类错误控制（FWER）**：通过Bonferroni、gate-keeping或other methods控制多重比较的假阳性率

### 3. 共享对照臂
```
传统设计：                    MAMS设计：
试验 A      试验 B            
Ctrl-A      Ctrl-B            
Tmt-A       Tmt-B            共享Ctrl
                               /    |    \
                            Arm1  Arm2  Arm3
```

**优势**：
- 减少对照组样本量需求
- 降低安慰剂伤害风险
- 更高效利用资源

### 4. 样本量重估（Sample Size Re-estimation）
- 基于中期分析的真实效应量更新样本量
- 不增加I型错误（当正确进行blind处理时）
- 提高研究有效性（当效应更大或更小于预期时）

## 关键设计参数

| 参数 | 含义 | 示例 |
|-----|------|------|
| **α（显著性水平）** | I型错误率 | 0.025（单尾）；多臂需要调整 |
| **β（检验力误差）** | II型错误率 | 0.10-0.20（对应80-90%检验力） |
| **效应量** | 临床上有意义的差异 | 缓解率：30% vs 50% |
| **中期分析时间点** | 何时进行interim analysis | 样本量25%, 50%, 75%处 |
| **停止边界** | futility和efficacy的阈值 | O'Brien-Fleming边界 |
| **共享对照比例** | 对照与干预的样本比 | 1:1或更高（取决于干预数） |

## MAMS在IBD中的应用

### 克罗恩病平台试验设计示例

**假设设计：**
- **总样本量**：600患者
- **臂数**：4个干预臂 + 1个共享对照臂（初期）
  - Arm 1: TNF拮抗剂单药
  - Arm 2: IL-23拮抗剂单药
  - Arm 3: TNF拮抗剂+IL-17拮抗剂组合
  - Arm 4: 小分子疗法（新增臂placeholder）
  - Control: 标准照护（抗TNF或现行best practice）

- **主要结局**：无皮质类固醇维持缓解 + 内镜无活动（1年）

- **中期分析**：
  - IA1 @ 25% enrollment（n=150）：评估futility，决定是否继续
  - IA2 @ 50% enrollment（n=300）：可能添加新臂，调整样本量
  - Final @ 100% enrollment + follow-up

- **停止规则示例**：
  - **Futility**: 若某臂vs Control的缓解率差<10%且上界CI不包含临床相关差异 → STOP该臂
  - **Efficacy**: 若某臂vs Control的缓解率>15%高于对照，且p<0.025 → DECLARE SUCCESS

### 优势
1. **时间效益**：不必等待全部600患者的1年随访，可在IA2进行中间性分析和决策
2. **样本效率**：共享对照减少无谓对照组样本
3. **伦理优越性**：无效臂快速停止，避免患者暴露于无效治疗
4. **灵活应对**：新治疗上市可动态添加（如新的小分子疗法）
5. **加速证据生成**：可能在3-4年内完成多个比较，而非多个独立5-10年试验

## 与其他设计的对比

| 设计 | 特点 | 适用场景 |
|-----|------|--------|
| **传统二臂RCT** | 固定，单一primary比较 | 明确的therapeutic question |
| **MAMS平台** | 多臂多阶段，共享对照，动态调整 | 多个治疗竞争，快速创新环境 |
| **Umbrella Trial** | 多臂按patient biomarker分层 | 靶向同一表型的不同亚型 |
| **Basket Trial** | 多臂按biomarker跨疾病分类 | 同一生物标志物的多个疾病 |

## 实施的关键要素

1. **生物统计学设计**
   - 提前注册试验设计和分析计划（SAP）
   - 明确的stopping boundaries和decision rules
   - Blind interim analysis（通常由独立DMC进行）

2. **监管与伦理**
   - IND/IDE的初期批准
   - 监管机构对interim modifications的接受程度
   - Ethics board的动态审查流程

3. **数据管理与分析**
   - 实时、高质量的数据管理
   - 预先编码的analysis programs（减少分析灵活性偏差）
   - 独立数据监测委员会（DMC）进行blinded interim reviews

4. **学科支持**
   - 经验丰富的生物统计学家
   - IBD领域的临床专家
   - Trial operations and coordinating center

## 历史与全球案例

### 早期成功案例
- **STAMPEDE** (前列腺癌, 2011-): 多臂多阶段platform，已评估20+干预臂
  - 加速了多种治疗方案的评估
  - 为多个新疗法的获批提供证据

### IBD中的应用前景
- ECCO 2024指南推荐IBD研究采纳MAMS/platform方法
- 正在规划的克罗恩病平台试验基于MAMS框架
- 与精准医学整合（biomarker-driven allocation）

## 关键局限与挑战

1. **复杂性**：设计与执行复杂，需高水平统计专业
2. **学习曲线**：监管机构、伦理部门和临床团队需要适应新模式
3. **资金承诺**：平台的长期性要求稳定的资金来源
4. **患者招募**：多臂设计可能增加信息负荷，需优化同意过程

## 关联连接

- [[Adaptive_Platform_Trial]] — 平台试验应用框架
- [[Pragmatic_Clinical_Trial_Design]] — 实用主义试验设计
- [[Crohn's_Disease]] — 在CD中的具体应用
- [[摘要-adaptive-platform-trial-cd]] — Nature 2025对CD平台试验的评述
- [[Precision_Medicine_IBD]] — 与生物标志物驱动设计的融合
