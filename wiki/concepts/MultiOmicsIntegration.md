---
title: "Multi-Omics Integration"
type: concept
tags: [methodology, bioinformatics, systems-biology]
sources: ["Clippings/Microbiome and metabolome features in inflammatory bowel disease via multi-omics integration analyses across cohorts 1.md"]
last_updated: 2026-04-28
---

# 多组学整合方法 (Multi-Omics Integration)

## 概述

多组学整合是将多种生物组学数据（如基因组学、代谢组学、蛋白质组学）结合起来，以全面理解复杂生物系统的方法。在 IBD 研究中，主要涉及：

1. **宏基因组学** (Metagenomics) — 菌群物种和功能基因
2. **代谢组学** (Metabolomics) — 粪便代谢物组成

## 核心方法

### 1. Cross-Cohort Integrative Analysis (CCIA)

**目的**：通过比较多个病例对照研究，评估疾病-菌群关联的健壮性，识别跨不同队列的一致关联。

**优势**：
- 最小化生物和技术混杂因素
- 提高发现的可重复性
- 验证跨多个地域和人群的特征

**实施步骤**：
1. 收集来自不同国家/地区的多个队列（本研究：9 个宏基因组队列 + 4 个代谢组队列）
2. 使用统一的生物信息学流程（MetaPhlan3 + HUMAnN3）进行重新处理
3. 统一代谢物命名（使用 HMDB ID）
4. 进行差异分析和特征选择

**数据规模**（本研究）：
- 宏基因组：1363 IBD 患者 + 对照组
- 代谢组：398 IBD 患者 + 对照组

### 2. Multi-Omics Biological Correlation (MOBC) Maps

**定义**：构建菌群、代谢物和功能基因之间的多维关联网络。

**实施步骤**：
1. 使用 KEGG 数据库建立代谢物与编码酶的基因之间的链接
2. 识别与代谢相关的 KO 基因（736 个）
3. 与差异分析识别的 KO 基因（162 个）进行交集分析
4. 获得 8 个既与代谢相关、又与疾病表型相关的核心 KO 基因

**生物学意义**：
- 识别微生物代谢通路缺陷
- 揭示宿主-菌群代谢互作机制
- 发现新的治疗靶点

## 关键分析工具

### 宏基因组分析

| 工具 | 功能 | 用途 |
|------|------|------|
| **KneadData** | 数据过滤 | 去除人类 DNA 污染 |
| **MetaPhlan3** | 物种分类学分析 | 物种鉴定与定量 |
| **HUMAnN3** | 功能分析 | 基因家族与通路分析 |

### 代谢组分析

| 方法 | 说明 |
|------|------|
| **Targeted Metabolomics** | Q300 代谢物阵列，检测 310 种标准物质 |
| **Untargeted Metabolomics** | 非靶向代谢组学，发现未知代谢物 |
| **UPLC-MS/MS** | 超高效液相层析-串联质谱 |

### 机器学习

| 模型 | 用途 |
|------|------|
| **Random Forest (RF)** | IBD 诊断分类 |
| **Iterative Feature Elimination (IFE)** | 特征选择，避免过拟合 |
| **Orthogonal Partial Least Squares-DA (OPLS-DA)** | 代谢组学样本差异分析 |

### 统计分析

| 方法 | 用途 |
|------|------|
| **PERMANOVA** | 多变量差异分析（β 多样性） |
| **Differential Abundance Analysis** | 单变量差异分析 |
| **FDR 校正** | 多重假设检验校正 |

## 诊断性能

### 单组学模型

| 组学类型 | 特征数 | 内部验证 AUROC | 独立验证 AUROC |
|---------|-------|----------------|----------------|
| **菌群物种** | 31 | 0.66-0.95 | 0.70-0.96 |
| **KO 基因** | 25 | 0.63-0.98 | 0.61-0.87 |
| **代谢物** | 13 | 0.94-0.95 | 0.84-0.87 |

### 多组学联合模型

- **菌群 + 代谢物** — 最佳性能
- **全部组学** (菌群 + KO 基因 + 代谢物)
  - Renji 队列：10-fold CV 达 AUROC 0.98，独立验证 0.96
  - USA-NL 队列：10-fold CV 达 AUROC 0.93，独立验证 0.92

### 疾病特异性

- 对结肠腺瘤 (Adenoma) — False Positive Rate: 0.04-0.15
- 对结直肠癌 (CRC) — False Positive Rate: 0.08-0.13
- 对 2 型糖尿病 (T2D) — False Positive Rate: 0.07-0.11

（说明生物标志物具有很好的疾病特异性）

## 关键发现

### 菌群层面

**74 种差异物种**：
- 31 种用于诊断的特征物种（主要来自厚壁菌门）
- 产丁酸菌显著减少
- 促炎菌显著增加

### 代谢物层面

**78 种差异代谢物**：
- 36-78 种在 IBD 患者中异常改变
- 涉及：氨基酸、脂肪酸、三羧酸循环中间产物
- 13 种用于诊断的特征代谢物

### 功能基因层面

**162 种差异 KO 基因**：
- 25 种用于诊断的特征基因
- 涉及 12 条关键通路（FDR < 0.05）
- 包括：Two-component system、Aminoacyl-tRNA 合酶通路

## 优势与局限性

### 优势

1. **样本量大、地域广** — 来自不同国家和地区的多个队列
2. **方法标准化** — 使用统一的生物信息学流程
3. **高诊断准确性** — AUROC 可达 0.92-0.98
4. **机制洞察** — 通过 MOBC 揭示宿主-菌群互作

### 局限性

1. **因果性未确定** — 关联性不代表因果关系
2. **混杂因素** — 饮食、药物、生活方式等因素未完全控制
3. **样本时间点** — 仅保留首次采样，难以反映动态变化

## 关联连接

- [[Inflammatory_Bowel_Disease]]
- [[GutMicrobiota]]
- [[Fecal Metabolites]]
- [[KEGG Database]]
- [[Machine Learning in Diagnostics]]
- [[qCD-S-microbiome-omics-integration]] — 微生物组学与多维Omic整合的临床实施框架
- [[Metagenomic_Sequencing]] — 宏基因组学方法与技术
- [[Population_Pharmacokinetics_IBD]] — 群体药代动力学整合应用
