---
title: "数据获取指南：IBD 微生物组公开数据库与下载"
type: source
tags: [操作指南, 数据获取, NCBI, SRA, 宏基因组]
sources: [Clippings/Noninvasive, microbiome-based diagnosis of inflammatory bowel disease.md]
last_updated: 2026-04-28
---

## 快速导航

本指南提供了**所有公开可获取的 IBD 微生物组数据**的下载方法和技术要点。

---

## 📥 BioProject 数据清单与直接链接

### ✅ 本研究新生成数据

| BioProject ID | 数据库 | 直接链接 | 样本类型 | 下载方式 |
|---------------|--------|--------|--------|--------|
| **PRJNA1086048** | NCBI SRA | [SRA 页面](https://www.ncbi.nlm.nih.gov/bioproject/?term=PRJNA1086048) | Illumina/MGI 宏基因组 | fasterq-dump/prefetch |

**数据特征**：
- 包含全球 13 个 IBD 队列的部分样本
- 推荐用于：诊断模型的独立验证、交叉验证

### ✅ 独立验证队列数据

| BioProject ID | 原始研究队列 | 地理位置 | 直接链接 | 样本类型 |
|---------------|-----------|---------|--------|--------|
| **PRJNA400072** | USA IBD 队列 | United States | [SRA 页面](https://www.ncbi.nlm.nih.gov/bioproject/?term=PRJNA400072) | 宏基因组 |
| **PRJNA429990** | Netherlands IBD 队列 | Netherlands | [SRA 页面](https://www.ncbi.nlm.nih.gov/bioproject/?term=PRJNA429990) | 宏基因组 |
| **PRJEB15371** | 欧洲多中心队列 | Spain, Denmark, UK | [ENA 页面](https://www.ebi.ac.uk/ena/browser/view/PRJEB15371) | 宏基因组 |

**数据特征**：
- 来自独立的研究小组，确保验证的客观性
- 包含 IBD 患者和多种对照组（健康、CRC、IBS、肥胖等）
- 推荐用于：外部验证、地理/种族亚组分析

---

## 🛠️ 技术工具与下载方法

### 方法 1：NCBI SRA Toolkit（推荐用于批量下载）

#### 安装

```bash
# macOS (Homebrew)
brew install sra-tools

# Ubuntu/Debian
sudo apt-get install sra-tools

# 验证安装
fastq-dump --version
```

#### 下载单个样本

```bash
# 方法 A：使用 fasterq-dump（更快，支持多线程）
fasterq-dump -e 8 SRR12345678  # 8 线程下载
# 输出: SRR12345678_1.fastq, SRR12345678_2.fastq (paired-end)

# 方法 B：使用 fastq-dump（备选）
fastq-dump --outdir ./fastq_data SRR12345678
```

#### 批量下载（整个 BioProject）

```bash
# 步骤 1：从 BioProject 获取 SRA Run 列表
# 访问 https://www.ncbi.nlm.nih.gov/bioproject/PRJNA1086048
# 点击 "Send to" → "Run Selector" → 下载 RunInfo.csv

# 步骤 2：提取所有 Run 账号
cut -d',' -f1 RunInfo.csv | tail -n +2 > run_ids.txt

# 步骤 3：批量下载
cat run_ids.txt | while read run; do
  echo "Downloading $run..."
  fasterq-dump -e 8 "$run" -O ./data/
done
```

### 方法 2：EBI ENA 浏览器（用于 PRJEB15371）

#### 在线浏览与下载

1. **访问** [ENA Browser](https://www.ebi.ac.uk/ena/browser/view/PRJEB15371)
2. **筛选样本**：按国家、疾病类型等条件筛选
3. **下载 Metadata**：导出样本信息表
4. **获取下载链接**：点击 Run，复制 FASTQ 链接

#### 批量下载脚本

```bash
# 从 ENA 下载样本列表（XML 格式）
wget "https://www.ebi.ac.uk/ena/data/view/PRJEB15371&display=xml" -O prjeb15371.xml

# 解析 XML 提取 FASTQ 下载链接
grep -oP 'fastq_aspera="\K[^"]+' prjeb15371.xml > download_links.txt

# 使用 aspera（高速下载工具，需单独安装）
cat download_links.txt | while read link; do
  ascp -i ~/.aspera/connect/etc/asperaweb_id_dsa.openssh -Tr -Q -l 300M \
    "era-fasp@fasp.sra.ebi.ac.uk:$link" ./fastq_data/
done
```

### 方法 3：Google Cloud + Terra（适用于大规模分析）

#### 使用 Terra 平台（无需本地下载）

```
1. 访问 https://terra.bio/
2. 搜索 "SRA" 或 "IBD microbiome" 工作流
3. 选择预配置的分析管道
4. 直接在云上运行分析，无需本地下载
```

---

## 📊 数据预处理与质控

### 质量评估

```bash
# 安装 FastQC
brew install fastqc  # macOS

# 运行质量检查
fastqc SRR12345678_1.fastq SRR12345678_2.fastq -o ./qc_results/

# 查看结果（HTML 报告）
open ./qc_results/SRR12345678_1_fastqc.html
```

### 去接头与低质量序列过滤

```bash
# 使用 Trimmomatic
java -jar trimmomatic-0.39.jar PE \
  SRR12345678_1.fastq SRR12345678_2.fastq \
  SRR12345678_1_trimmed.fastq SRR12345678_1_unpaired.fastq \
  SRR12345678_2_trimmed.fastq SRR12345678_2_unpaired.fastq \
  ILLUMINACLIP:TruSeq3-PE.fa:2:30:10 \
  LEADING:3 TRAILING:3 SLIDINGWINDOW:4:15 MINLEN:36
```

---

## 🔬 宏基因组分类与物种分配

### 方法 1：使用 QIIME2（推荐）

```bash
# 安装 QIIME2
conda install -c qiime2 qiime2=2026.4

# 导入数据
qiime tools import \
  --type SampleData[PairedEndSequencesWithQuality] \
  --input-path ./fastq_data \
  --input-format CasavaOneEightSingleLanePerSampleDirFmt \
  --output-path demux-paired-end.qza

# 质量过滤与去噪（DADA2）
qiime dada2 denoise-paired \
  --i-demultiplexed-seqs demux-paired-end.qza \
  --p-trim-left-f 0 \
  --p-trim-left-r 0 \
  --p-trunc-len-f 240 \
  --p-trunc-len-r 160 \
  --o-representative-sequences rep-seqs.qza \
  --o-table table.qza \
  --o-denoising-stats stats.qza

# 物种分类（使用 SILVA 数据库）
qiime feature-classifier classify-sklearn \
  --i-classifier silva-138-99-nb-classifier.qza \
  --i-reads rep-seqs.qza \
  --o-classification taxonomy.qza
```

### 方法 2：使用 Kraken2（快速分类）

```bash
# 安装 Kraken2 和 Bracken
conda install -c bioconda kraken2 bracken

# 下载 SILVA 数据库用于 Kraken2
kraken2-build --special silva --db silva_db

# 运行分类
kraken2 --db silva_db --paired \
  SRR12345678_1.fastq SRR12345678_2.fastq \
  --output kraken_output.txt

# 使用 Bracken 进行丰度估计
bracken -d silva_db -i kraken_output.txt \
  -o bracken_output.txt -l S  # S = 种级
```

---

## 📈 生成特征表与元数据矩阵

### 创建菌群丰度表

```bash
# 使用 QIIME2 导出
qiime tools export \
  --input-path table.qza \
  --output-path exported_table

# 输出格式：feature-table.biom (BIOM 格式)
# 可转换为 TSV 格式用于下游分析
biom convert -i feature-table.biom \
  -o otu_table.tsv --to-tsv
```

### 准备诊断模型的输入数据

```bash
# 提取关键的 10 (UC) + 9 (CD) 种菌
# 假设 otu_table.tsv 已准备好

python << 'EOF'
import pandas as pd
import numpy as np

# 读取 OTU 表
otu_table = pd.read_csv('otu_table.tsv', sep='\t', index_col=0)

# 定义 UC 和 CD 的生物标志物菌种
uc_biomarkers = [
    "Gemella_morbillorum",
    "Blautia_hansenii", 
    "Actinomyces_sp_oral_taxon_181",
    "Clostridium_spiroforme",
    "Clostridium_leptum",
    "Fusicatenibacter_saccharivorans",
    "Gemmiger_formicilis",
    "Ruminococcus_torques",
    "Odoribacter_splanchnicus",
    "Bilophila_wadsworthia"
]

cd_biomarkers = [
    "Bacteroides_fragilis",
    "Escherichia_coli",
    "Actinomyces_sp_oral_taxon_181",
    "Roseburia_inulinivorans",
    "Blautia_obeum",
    "Lawsonibacter_asaccharolyticus",
    "Roseburia_intestinalis",
    "Dorea_formicigenerans",
    "Eubacterium_sp_CAG_274"
]

# 提取并规范化
biomarker_table = otu_table.loc[otu_table.index.isin(uc_biomarkers + cd_biomarkers)]

# 相对丰度转换（百分比）
biomarker_relative = biomarker_table.div(biomarker_table.sum(axis=0), axis=1) * 100

# 保存为诊断模型输入
biomarker_relative.to_csv('biomarker_input.csv')
print("✅ 诊断模型输入数据已生成")

EOF
```

---

## 🔗 推荐的完整分析流程脚本

```bash
#!/bin/bash
# IBD_microbiome_analysis.sh
# 完整的从原始数据到诊断预测的分析流程

set -e  # 遇到错误停止

# 配置
BIOPROJECT="PRJNA1086048"
OUTPUT_DIR="./ibd_microbiome_analysis"
THREADS=8
REFERENCE_DB="silva"

# 步骤 1：创建目录结构
mkdir -p $OUTPUT_DIR/{raw_fastq,qc,processed,results}

# 步骤 2：下载数据
echo "⏳ Downloading SRA data for $BIOPROJECT..."
prefetch -p $BIOPROJECT --max-size 100G -O $OUTPUT_DIR/raw_fastq

# 步骤 3：转换为 FASTQ
echo "⏳ Converting to FASTQ..."
for sra_file in $OUTPUT_DIR/raw_fastq/*/*.sra; do
  fasterq-dump -e $THREADS "$sra_file" -O $OUTPUT_DIR/raw_fastq
done

# 步骤 4：质控
echo "⏳ Running QC..."
fastqc $OUTPUT_DIR/raw_fastq/*.fastq -o $OUTPUT_DIR/qc -t $THREADS

# 步骤 5：分析（使用 QIIME2）
echo "⏳ Processing with QIIME2..."
# [详见上文 QIIME2 命令]

# 步骤 6：分类
echo "⏳ Taxonomic classification..."
# [详见上文 Kraken2 或 QIIME2 分类命令]

# 步骤 7：诊断预测
echo "⏳ IBD diagnostic prediction..."
python biomarker_prediction.py \
  --input $OUTPUT_DIR/results/biomarker_input.csv \
  --model pretrained_ibd_model.pkl \
  --output $OUTPUT_DIR/results/diagnostic_predictions.csv

echo "✅ Analysis complete! Results saved to $OUTPUT_DIR/results/"
```

---

## 💾 数据存储与备份建议

### 本地存储
```
推荐配置：
├─ 原始 FASTQ：200 GB/1000 样本
├─ 处理后数据：50 GB/1000 样本  
├─ 分析结果：10 GB/1000 样本
└─ 总计：~260 GB/1000 样本

实用工具：
- 外置硬盘 (1-2 TB USB 3.0) 或
- NAS 存储 (10+ TB，支持 RAID 1 备份)
```

### 云存储选项
```
AWS S3:
- 成本：约 $0.023/GB/月
- 优势：与 AWS EC2 分析免带宽费用

Google Cloud Storage:
- 成本：约 $0.020/GB/月  
- 优势：与 Terra/Nextflow 集成

本地学术网盘：
- 优先使用所属机构的网盘
- 确保满足数据隐私与安全要求
```

---

## 📝 元数据收集清单

下载数据后，需要补充收集的元数据：

- [ ] 患者年龄、性别、种族/民族
- [ ] IBD 类型 (UC vs CD)、诊断年份
- [ ] 疾病活动性评分 (Mayo score, CDAI)
- [ ] 当前/既往治疗方案
- [ ] 采样日期、样本编号
- [ ] 肠镜评分、组织病理学评分（如有）
- [ ] 粪钙卫蛋白水平（如有）
- [ ] 膳食信息、抗生素使用情况
- [ ] 遗传背景信息（如有）

---

## ⚠️ 常见问题与排查

### Q1: 下载速度太慢怎么办？
**A**: 使用 aspera 工具（高速 UDP 协议）替代 HTTPS，或切换到 Google Cloud / Terra 云平台

### Q2: SRA 数据不提供已处理的物种表怎么办？
**A**: 使用上文提供的 QIIME2 或 Kraken2 流程进行处理；或查看是否有补充文件 (Supplementary Data)

### Q3: 原始论文未发布预训练模型怎么办？
**A**: 联系通讯作者请求模型权重；或基于论文描述的菌种子集重新训练

### Q4: 某个队列的元数据不完整怎么办？
**A**: 使用最小化数据集进行分析；标注缺失数据；或直接联系原始研究者获取

---

## 🔗 进阶资源

- **SRA 官方指南**：https://www.ncbi.nlm.nih.gov/books/NBK158899/
- **QIIME2 完整教程**：https://docs.qiime2.org
- **Kraken2 手册**：https://github.com/DerrickWood/kraken2/wiki
- **ENA 数据检索**：https://www.ebi.ac.uk/ena/

---

## 关联连接

- [[Data_Availability_IBD_Microbiome]] — 多中心验证框架
- [[Metagenomic_Sequencing]] — 技术背景
- [[摘要-microbiome-based-ibd-diagnosis]] — 原始研究
