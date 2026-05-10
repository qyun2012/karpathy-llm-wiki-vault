---
title: "Microbiome and Metabolome in IBD via Multi-Omics Integration"
type: source
tags: [IBD, microbiome, metabolome, multi-omics, biomarkers]
sources: ["Clippings/Microbiome and metabolome features in inflammatory bowel disease via multi-omics integration analyses across cohorts 1.md"]
last_updated: 2026-04-28
---

# 摘要：多组学整合分析中的微生物组和代谢组特征

**期刊** — Nature Communications  
**发表日期** — 2023-11-06  
**通讯作者** — Jing-Yuan Fang, Haoyan Chen, Jie Hong  
**研究团队** — 上海交通大学医学院附属仁济医院  
**DOI** — [s41467-023-42788-0](https://www.nature.com/articles/s41467-023-42788-0)

## 研究背景

虽然已有研究报告了肠道菌群和代谢物与 IBD 的关联，但不同研究之间的不一致结论阻碍了对其诊断价值的理解。本研究通过跨队列整合分析，系统地比较 9 个宏基因组队列和 4 个代谢组队列数据，以识别一致的 IBD 诊断生物标志物。

## 核心方法

### 样本规模

- **宏基因组队列**：6 个发现队列 + 3 个验证队列，共 1363 个 IBD 患者
- **代谢组队列**：2 个靶向 + 2 个非靶向代谢组学，共 398 个 IBD 患者
- **队列来源**：中国、美国、欧洲等多个国家和地区

### 分析策略

1. **Cross-Cohort Integrative Analysis (CCIA)** — 识别跨队列的一致特征
2. **差异丰度分析** — 识别显著改变的菌群和代谢物（FDR < 0.0001）
3. **机器学习** — Random Forest + Iterative Feature Elimination 进行特征选择与诊断建模
4. **Multi-Omics Biological Correlation (MOBC) Maps** — 构建菌群-代谢物-基因关联网络

## 主要发现

### 1. 菌群特征（31 种诊断标志物）

#### 显著减少的益生菌
- **产丁酸菌** — Faecalibacterium prausnitzii, Roseburia intestinalis, Eubacterium hallii, Gemmiger formicilis, Eubacterium rectale, Ruminococcus bromii
  - 意义：丁酸是肠上皮细胞的主要能量来源，可以维持肠屏障完整性
- **矿物质代谢菌** — Collinsella aerofaciens（涉及铁代谢）
- **胆酸代谢菌** — Ruminococcus torques
- **尿素循环菌** — Bifidobacterium longum
- **抗炎菌** — Alistipes putredinis（与 Candida albicans 竞争）

#### 新发现的关键菌种（罕见报告）
- **Asaccharobacter celatus** — 产生马尿酚 (Equol)，可缓解自身免疫脑脊髓炎
- **Gemmiger formicilis** — 产丁酸菌
- **Erysipelatoclostridium ramosum** — 在 IBD 中更普遍，但作用机制待研究

#### 显著增加的病原菌
- Ruminococcus gnavus — 产生促炎多糖和黏液降解酶，破坏肠粘膜屏障
- Bacteroides fragilis
- Escherichia coli
- Clostridium innocuum — 与 CD 中肠狭窄相关，万古霉素耐药

### 2. 代谢物特征（13 种诊断标志物）

#### 差异代谢物总体特征

发现 78 种差异代谢物，其中 36 种仅在内部队列中独有：

| 代谢物类别 | 特征 | 临床意义 |
|----------|------|--------|
| **氨基酸** | 色氨酸、谷氨酰胺、精氨酸增加 | Tryptophan 涉及免疫调控 |
| **代谢产物** | 1-甲基组氨酸、肉碱升高 | 与肉类消费相关（已知 IBD 风险因素） |
| **TCA 循环产物** | 丙酮酸、富马酸、草酰乙酸异常积累 | 表明菌群能量代谢异常 |
| **苯类化合物** | 酚基吡酮酸、3-羟基苯基乙酸升高 | 作用机制未知 |

#### 诊断性能
- 13 种特征代谢物构建的模型：AUROC 0.94-0.95（Renji 队列）、0.84-0.87（验证队列）
- **高于** 菌群和 KO 基因模型

### 3. 功能基因特征（25 种诊断标志物）

#### 关键通路（共 162 个差异 KO 基因）

**上调通路**（4 条）：
1. **Two-component system** — 细菌信号转导和毒力因子调控
   - 关键基因：crp (K10914, CRP/FNR 转录因子)
   - 与粪便钙卫蛋白正相关
   - 可作为治疗靶点
2. Cell cycle – Caulobacter
3. Lipopolysaccharide biosynthesis
4. **Aminoacyl-tRNA biosynthesis** — 蛋白质合成和免疫调控
   - 关键基因：aspS (K09759), ileS (K01870), hisS (K01892), valS (K01873)
   - Akkermansia muciniphila 分泌的 seryl-tRNA 合酶促进抗炎 IL-10 产生

**下调通路**（8 条）：
- Propanoate metabolism
- Phosphotransferase system (PTS)
- Glycolysis/Gluconeogenesis
- Biosynthesis of amino acids

### 4. Multi-Omics 关联分析（MOBC Maps）

#### 微生物代谢转化缺陷（8 个核心 KO 基因）

| 基因 | 功能 | IBD 中的问题 | 临床后果 |
|------|------|-----------|---------|
| **K22477 (argO)** | N-乙酰谷氨酸合酶 | 表达下降 | L-谷氨酸积累 → 腹痛、腹泻 |
| **K02373 (larA)** | 乳酸消旋酶 | 表达下降 | (S)-乳酸无法转化 → 肠道炎症 |
| **K00290 (LYS1)** | 沙克哈拌脱氢酶 | 表达下降 | 抗氧化能力减弱 → 氧化应激加重 |
| **K01476 (rocF)** | 精氨酸酶 | 表达下降 | 尿素代谢异常 → 粘膜屏障损伤 |

**Aminoacyl-tRNA 合酶的免疫调控功能**：
- 超越翻译的"非经典"功能
- 可能通过分泌型 ARS 调控宿主免疫和肠道稳态

## 诊断模型性能

### 单组学模型

| 数据类型 | 特征数 | 发现队列 AUROC | 验证队列 AUROC |
|---------|-------|--------------|--------------|
| 菌群物种 | 31 | 0.66-0.95 | 0.70-0.96 |
| KO 基因 | 25 | 0.63-0.98 | 0.61-0.87 |
| 代谢物 | 13 | 0.94-0.95 | 0.84-0.87 |

### 多组学联合模型

**最优：菌群 + 代谢物 + KO 基因**

- **Renji 队列**：10-fold CV = 0.98，独立验证 = 0.96
- **USA-NL 队列**：10-fold CV = 0.93，独立验证 = 0.92

### IBD 亚型区分

12 个多组学特征可区分 UC 和 CD：
- 内部队列 AUROC ≈ 0.8
- 验证队列 AUROC > 0.7

### 疾病特异性（与其他肠道疾病的假阳性率）

| 疾病 | 菌群模型 FPR | KO 基因模型 FPR | 代谢物模型 FPR |
|------|----------|------------|-----------|
| 结肠腺瘤 | 0.15 | 0.04 | 未测 |
| CRC | 0.08-0.13 | 0.13 | 未测 |
| T2D | 0.11 | 0.07 | 未测 |

（说明极好的疾病特异性）

## 临床意义

1. **非侵入式诊断** — 相比结肠镜检查的金标准，粪便生物标志物更便利
2. **早期发现** — 提前识别 IBD 患者，便于及时干预
3. **亚型鉴别** — 区分 UC 和 CD，指导个性化治疗
4. **机制洞察** — 发现微生物代谢障碍和免疫调控靶点
5. **治疗靶点** — crp、Aminoacyl-tRNA 合酶等新的药物靶点

## 研究局限性

1. **因果性未确立** — 无法确定菌群变化是原因还是结果
2. **混杂因素控制不完全** — 饮食、药物、生活方式等难以完全控制
3. **纵向数据缺乏** — 仅保留首次采样，无法追踪动态变化
4. **队列选择偏差** — 可能存在的患者选择偏差

## 后续研究需求

- 纵向随访研究，追踪菌群和代谢物的动态变化
- 干预研究，验证菌群和代谢物调节对 IBD 的治疗效果
- 基础研究，阐明关键菌种和通路的机制
- 临床验证，在大规模人群中验证诊断模型

## 📊 数据可用性

### 本研究生成的原始数据

**宏基因组数据**：
- 存储库：China National Center for Bioinformation (CNCB)
- Accession Code：**PRJCA017408**
- 样本量：208 人（IBD=138, Control=70）

**代谢组数据**：
- 存储库：MetaboLights (EMBL-EBI)
- Accession Code：**MTBLS8713**
- 样本量：178 人（IBD=135, Control=43）

### 验证队列数据（公开可获取）

**宏基因组验证队列**（8 个额外项目）：
- curatedMetagenomicData (Bioconductor) 中 5 个项目
- ENA (European Nucleotide Archive) 中 3+ 个项目
- 共计 1,363 个 IBD 患者样本

**代谢组验证队列**：
- 期刊补充材料（2 个外部队列）
- GitHub 仓库（非 IBD 对照队列）：https://github.com/borenstein-lab/microbiome-metabolome-curated-data

### 参考数据库

- HMDB (Human Metabolome Database)：https://hmdb.ca/
- 用于统一代谢物名称与编码

详见：[[数据获取指南-microbiome-ibd-multiomics]]

---

## 关联连接

- [[Inflammatory_Bowel_Disease]]
- [[MultiOmicsIntegration]]
- [[GutMicrobiota]]
- [[Fecal Metabolites]]
- [[Two-Component System]]
- [[Aminoacyl-tRNA Synthetases]]
- [[数据获取指南-microbiome-ibd-multiomics]]
