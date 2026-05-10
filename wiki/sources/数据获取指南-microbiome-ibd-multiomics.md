---
title: "Data Availability Guide - Microbiome IBD Multi-Omics"
type: source
tags: [data-access, bioinformatics, databases, open-science]
sources: ["Clippings/Microbiome and metabolome features in inflammatory bowel disease via multi-omics integration analyses across cohorts 1.md"]
last_updated: 2026-04-28
---

# IBD 多组学研究的数据获取指南

## 🔓 原始研究数据（本研究生成）

### 1. 宏基因组数据

**存储库**：China National Center for Bioinformation (CNCB)  
**Accession Code**：**PRJCA017408**  
**URL**：https://db.cngb.org/search/project/PRJCA017408

**数据内容**：
- 宏基因组测序原始数据（raw sequencing reads）
- 来自 Renji Hospital 两个校区（Puxi + Pudong）的 IBD 患者和健康对照
- 使用 NovaSeq6000 平台（Illumina）测序

**样本量**：
- Puxi 队列：n=132（IBD=87, Control=45）
- Pudong 队列：n=76（IBD=51, Control=25）
- 共计：n=208（IBD=138, Control=70）

**访问方式**：
```bash
# 示例：使用 aspera 高速下载
ascp -QT -l 300m -P33001 -i ~/.aspera/connect/etc/asperaweb_id_dsa.openssh \
  era-fasp@fasp.sra.ebi.ac.uk:vol1/... /local/path/
```

---

### 2. 代谢组数据

**存储库**：MetaboLights (EMBL-EBI)  
**Accession Code**：**MTBLS8713**  
**URL**：https://www.ebi.ac.uk/metabolights/MTBLS8713

**数据内容**：
- 代谢组学质谱原始数据（mass spectrometry raw files）
- 来自 Renji Hospital 的靶向代谢组学数据

**数据类型**：
- **靶向代谢组学** — 使用 Q300 Metabolite Array Kit
- **检测物质** — 310 种标准物质，12 个亚类
- **分析方法** — UPLC-MS/MS（超高效液相-串联质谱）

**样本量**：
- Puxi 队列：n=108（IBD=83, Control=25）
- Pudong 队列：n=70（IBD=52, Control=18）
- 共计：n=178（IBD=135, Control=43）

**访问方式**：
```bash
# 从 MetaboLights 下载
wget -r https://www.ebi.ac.uk/metabolights/MTBLS8713/
# 或使用 FTP
ftp ftp.ebi.ac.uk
# 导航到 /pub/metabolights/MTBLS8713/
```

---

## 📊 公开数据库（验证队列）

### 宏基因组数据来源（9 个队列）

#### 通过 curatedMetagenomicData 获取（推荐）

**项目名**：curatedMetagenomicData  
**URL**：https://bioconductor.org/packages/curatedMetagenomicData  
**安装方式**（R/Bioconductor）：
```r
# R 包安装
if (!require("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

BiocManager::install("curatedMetagenomicData")

# 加载数据
library(curatedMetagenomicData)

# 列出所有可用数据集
curatedMetagenomicData()

# 获取特定数据集
ibd_data <- curatedMetagenomicData(
    pattern = "^.*HMP_2019_ibdmdb.*",
    dryrun = FALSE
)
```

**包含的 IBD 队列**：

| NCBI Accession | 项目 ID | 样本数 | 区域 | 说明 |
|---|---|---|---|---|
| **PRJNA385949** | HallAB 2017 | ~154 | USA | 独立验证队列 |
| **PRJEB1220** | NielsenHB 2014 | ~125 | 欧洲 | 发现队列 |
| **PRJNA398089** | HMP 2019 ibdmdb | ~489 | USA | 发现+验证队列（最大） |
| **EGAS00001001704** | LifeLD VilaAV 2018 | ~156 | 多国 | 发现队列 |
| **EGAD00001004194** | LifeLD VilaAV 2018 | 见上 | 同上 | 基因型数据 |

#### 通过欧洲核苷酸档案库 (ENA) 获取

**URL**：https://www.ebi.ac.uk/ （或 https://www.ebi.ac.uk/ena/）

**包含的队列**：

| NCBI Accession | 项目名 | 样本数 | 特点 |
|---|---|---|---|
| **PRJNA400072** | FranzosaEA 2019A/2019B | ~145 | 发现队列，高质量 |
| **PRJEB15371** | HeQ 2017 | ~98 | 验证队列 |
| **PRJEB27928** | ~ | ~ | 扩展验证 |
| **PRJEB1786** | ~ | ~ | 扩展验证 |
| **PRJEB7774** | ~ | ~ | 扩展验证 |

**ENA 批量下载脚本**：
```bash
#!/bin/bash
# 下载 PRJNA400072 的所有数据
ACCESSION="PRJNA400072"

# 方法 1：使用 ENA 元数据 API
curl -s "https://www.ebi.ac.uk/ena/portal/api/filereport?accession=${ACCESSION}&result=read_run&fields=run_accession,fastq_ftp&format=tsv" \
  | tail -n +2 | while read run ftp; do
    wget -q ftp://${ftp}
done

# 方法 2：使用 sra-tools
prefetch --ascp-path="/usr/bin/ascp|/opt/asperaweb_id_dsa.openssh" \
  --max-size=1000000000 \
  $(esearch -db sra -query "${ACCESSION}" | efetch -format runinfo | cut -d',' -f1 | tail -n+2)

fastq-dump --split-files <SRA_file>
```

---

### 代谢组数据来源（4 个队列）

#### 1. 靶向代谢组学数据（本研究 + 外部队列）

**来源**：

| 数据来源 | 样本数 | 数据库 | 访问方式 |
|---------|-------|--------|--------|
| **本研究** (Renji) | 178 | MetaboLights MTBLS8713 | https://www.ebi.ac.uk/metabolights/MTBLS8713 |
| **外部队列 1** | 110 | 已发表论文补充材料 | 见原文献 Supplementary Materials |
| **外部队列 2** | 110 | 已发表论文补充材料 | 见原文献 Supplementary Materials |

#### 2. 非靶向代谢组学数据

**来源**：

| 数据来源 | 获取方式 | URL |
|---------|--------|-----|
| **外部公开队列** | MetaboLights | https://www.ebi.ac.uk/metabolights/ |
| **非 IBD 对照队列** (CRC, Adenoma, T2D, T1D) | GitHub 仓库 | https://github.com/borenstein-lab/microbiome-metabolome-curated-data |

**获取非 IBD 对照数据**（用于特异性验证）：
```bash
# Clone 仓库
git clone https://github.com/borenstein-lab/microbiome-metabolome-curated-data.git

# 包含的数据集
# - Colorectal Cancer (CRC) — 2 个队列
# - Adenoma — 1 个队列
# - Type 1 Diabetes (T1D) — 1 个队列
```

---

## 🔬 参考数据库

### Human Metabolome Database (HMDB)

**URL**：https://hmdb.ca/  
**功能**：代谢物鉴定与注释（本研究用于统一代谢物 ID）

**使用方式**：
```bash
# HMDB API 查询
curl "https://hmdb.ca/api/v1/metabolites.json" \
  -H "Content-Type: application/json" \
  -d '{"query": "glucose"}'

# HMDB 数据库下载
wget https://hmdb.ca/system/downloads/current/hmdb_metabolites.csv
```

**在本研究中的应用**：
- 79 个共同代谢物的识别（4 个队列）
- 代谢物名称的统一编码
- SMILES 结构式获取用于后续分析

---

## 📋 完整数据摘要表

### 宏基因组队列总览（n=1,363 IBD 患者）

| 队列编号 | 项目 ID | 样本数 | 发现/验证 | 国家 | 数据库 | 访问链接 |
|---------|--------|-------|---------|------|--------|--------|
| 1 | PRJCA017408 | 208 | 发现+验证 | 中国 | CNCB | https://db.cngb.org/search/project/PRJCA017408 |
| 2 | PRJNA385949 | 154 | 验证 | USA | curatedMetagenomicData | Bioconductor |
| 3 | PRJEB1220 | 125 | 发现 | 欧洲 | curatedMetagenomicData | Bioconductor |
| 4 | PRJNA398089 | 489 | 发现+验证 | USA | curatedMetagenomicData | Bioconductor |
| 5 | EGAS00001001704 | 156 | 发现 | 多国 | curatedMetagenomicData | Bioconductor |
| 6 | PRJNA400072 | 145 | 发现 | USA | ENA | https://www.ebi.ac.uk/ena/ |
| 7 | PRJEB15371 | 98 | 验证 | 欧洲 | ENA | https://www.ebi.ac.uk/ena/ |
| 8 | PRJEB27928 | ~ | 验证 | ~ | ENA | https://www.ebi.ac.uk/ena/ |
| 9 | PRJEB1786/7774 | ~ | 验证 | ~ | ENA | https://www.ebi.ac.uk/ena/ |

### 代谢组队列总览（n=398 IBD 患者）

| 队列编号 | 数据类型 | 样本数 | 数据库 | Accession | 访问链接 |
|---------|---------|-------|--------|-----------|--------|
| 1 | 靶向代谢组学 | 178 | MetaboLights | MTBLS8713 | https://www.ebi.ac.uk/metabolights/MTBLS8713 |
| 2 | 靶向代谢组学 | 110 | 期刊补充材料 | 见论文 | 论文辅助材料 |
| 3 | 非靶向代谢组学 | 110 | 期刊补充材料 | 见论文 | 论文辅助材料 |

---

## 🛠️ 快速获取工作流

### 工作流 1：仅获取本研究数据

```bash
#!/bin/bash
# 创建工作目录
mkdir -p ibd_multiomics_data && cd ibd_multiomics_data

# 1. 宏基因组数据
echo "下载宏基因组数据 (PRJCA017408)..."
# 使用 CNCB 提供的下载脚本或手动访问
# https://db.cngb.org/search/project/PRJCA017408

# 2. 代谢组数据
echo "下载代谢组数据 (MTBLS8713)..."
wget -r https://www.ebi.ac.uk/metabolights/MTBLS8713/ \
  -O metabolomics_raw_data/

echo "✓ 数据下载完成"
```

### 工作流 2：获取所有验证队列（大规模）

```bash
#!/bin/bash
# 使用 R + curatedMetagenomicData（推荐）

R --slave << 'REOF'
# 安装
BiocManager::install("curatedMetagenomicData")
library(curatedMetagenomicData)

# 列出所有 IBD 数据集
ibd_datasets <- curatedMetagenomicData(
    pattern = "^.*ibd|^.*crohn|^.*colitis",
    dryrun = FALSE
)

# 提取元数据
metadata <- attr(ibd_datasets, "metadata")
write.csv(metadata, "ibd_metadata.csv")

# 保存数据
saveRDS(ibd_datasets, "ibd_combined_data.rds")
REOF
```

### 工作流 3：ENA 大规模批量下载

```bash
#!/bin/bash
# 使用 ENA 的 REST API 和 wget

PROJECTS=("PRJNA400072" "PRJEB15371" "PRJEB27928")

for PROJECT in "${PROJECTS[@]}"; do
  echo "Downloading $PROJECT..."
  
  # 获取文件列表
  curl -s "https://www.ebi.ac.uk/ena/portal/api/filereport?accession=${PROJECT}&result=read_run&fields=run_accession,fastq_ftp&format=tsv" \
    | tail -n +2 | while read -r RUN FTP; do
      wget -P "./${PROJECT}" "ftp://${FTP}"
    done
done
```

---

## ⚠️ 数据质量与使用指南

### 预处理步骤（已在原研究中完成）

1. **宏基因组**
   - KneadData — 去除人类 DNA 污染
   - MetaPhlan3 — 物种分类学分析
   - HUMAnN3 — 功能基因分析 (KO 基因注释)

2. **代谢组**
   - QuanMET 软件 — 峰值积分与定量
   - 与 HMDB 比对 — Level 1 置信度鉴定
   - 质量控制 — 每 14 样重复注入 QC 样本

### 数据引用格式

**宏基因组**：
> Microbiome data generated in this study have been deposited in the China National Center for Bioinformation database under accession code PRJCA017408.

**代谢组**：
> Metabolomics mass spectrometry data have been deposited in MetaboLights under accession code MTBLS8713 (https://www.ebi.ac.uk/metabolights/MTBLS8713).

### 伦理与开放获取

- ✅ 所有数据已开放，无需申请权限
- ✅ 符合 FAIR 原则（Findable, Accessible, Interoperable, Reusable）
- ✅ 建议引用原论文：Ning et al., Nature Commun. 2023

---

## 关联连接

- [[摘要-microbiome-ibd-multiomics]]
- [[MultiOmicsIntegration]]
- [[GutMicrobiota]]
- [[Fecal Metabolites]]
- [[KEGG Database]]
