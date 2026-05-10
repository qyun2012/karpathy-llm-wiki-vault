---
title: "Jonathan Golob"
type: entity
tags: [研究者, 微生物组, IBD, 大学密歇根]
sources: ["Clippings/The Microbiome in Quiescent Crohn's Disease With Persistent Symptoms Show Disruptions in Microbial Sulfur and Tryptophan Pathways.md"]
last_updated: 2026-05-02
---

## 身份

**Jonathan Golob** 是美国微生物组研究领域的领先研究者，现任职于**密歇根大学医学院**（University of Michigan Medical School）。

## 主要研究方向

### 1. 克罗恩病微生物组学
- 聚焦于**静止期克罗恩病中的微生物群落失调**
- 特别关注：
  - 微生物多样性与患者症状的关联
  - 代谢通路失调与屏障功能破坏的机制
  - 色氨酸和硫代谢的役色

### 2. 宏基因组学方法论
- 开发并维护 **geneshot** 流程：
  - 全基因组鸟枪法宏基因组测序分析的开源 Nextflow 管道
  - 支持 de novo 基因组组装和功能注释
  - 无需依赖参考数据库的独立分析能力
  - GitHub 开源资源：[https://github.com/Golob-Minot/geneshot](https://github.com/Golob-Minot/geneshot)

### 3. 多中心队列研究
- 参与 **SPARC IBD**（前瞻性成人 IBD 研究队列）
- 多地理、多种族、多民族的大规模患者群组
- 标准化的样本处理和测序（单一参考实验室）

## 代表性研究成果

### 静止期克罗恩病与硫色氨酸代谢研究（2024）

**文献标识**：
- **标题**：The Microbiome in Quiescent Crohn's Disease With Persistent Symptoms Show Disruptions in Microbial Sulfur and Tryptophan Pathways
- **期刊**：Gastro Hep Advances, Vol. 3, Issue 2, Pages 167-177
- **出版年**：2024
- **DOI**：10.1016/j.gastha.2023.11.005
- **预印版**：https://doi.org/10.1101/2023.05.16.23290065

**研究设计**：
- 多中心观察性研究
- 患者队列（n=424）：
  - qCD+S（持续症状的静止 CD）：39 例
  - qCD-S（无症状的静止 CD）：274 例
  - aCD（活跃 CD）：21 例
  - IBS-D（腹泻型肠易激综合征）：40 例
  - HC（健康对照）：50 例

**技术与方法**：
- 全基因组鸟枪法宏基因组测序
- geneshot 管道进行 de novo 基因组组装
- HUMAnN3 功能分析（基于 KEGG 正交数据库）
- Shannon 多样性、Jaccard/Bray-Curtis 距离计算
- ANCOM-BC 差异丰度分析
- 随机森林分类模型用于预测

**主要发现**：
1. **微生物多样性丧失**：qCD+S 患者 Shannon 指数显著下降
2. **微生物群落结构改变**：β-多样性显著不同于 qCD-S
3. **口腔菌群过度**：链球菌、Rothia dentocariosa、Fusobacterium nucleatum 富集
4. **丁酸和吲哛产生菌耗竭**：直肠真杆菌和粪便杆菌减少
5. **色氨酸代谢通路破坏**：
   - tnaA 基因（色氨酸酶）显著减少
   - tnaA 等位基因失多样化（聚类分析）
6. **硫代谢失调**：半胱氨酸、蛋氨酸、ATP 转运通路异常
7. **预测模型**：微生物物种可预测 qCD+S vs qCD-S（AUC=0.72）

**临床意义**：
- 揭示非炎症驱动的症状机制
- 识别潜在的微生物生物标志物
- 为菌群定向治疗提供靶点

## 学术贡献与影响

### 1. 方法论创新
- **geneshot** 的开发使得 de novo 宏基因组分析成为可能
- 减少对参考数据库的依赖，提高发现新基因功能的能力
- 开源共享，支持全球科研社区

### 2. 队列研究设计
- 参与 SPARC IBD 的标准化和质量控制
- 强调跨地理、跨民族的大规模样本
- 建立可复现的生物样本库和数据共享

### 3. 生物标志物发现
- 系统鉴定微生物物种与患者表型的关联
- 从物种水平升级到功能基因水平（tnaA）的精准分析
- 从横截面到纵向轨迹的方向发展

## 研究伦理与数据共享

### 伦理认证
- 密歇根大学机构审查委员会批准：HUM193179

### 数据透明度
- 所有测序数据通过 **IBD Plexus** 计划提供
- GitHub 完整发布分析流程和脚本：
  - https://github.com/Golob-Minot/geneshot
  - https://github.com/aalee1/ibd-sparc.git
- 支持研究重复和衍生研究

## 团队协作

在 qCD 研究中的主要合作者：
- **Krishna Rao** — 共同一作，数据分析
- **Shrinivas Bishu** — 共同一作，统计方法
- **Allen A. Lee** — 通讯作者，PI

## 未来研究方向（推测）

基于已发表研究，可预期的方向：
1. **纵向研究**：追踪 qCD+S 患者微生物学变化与症状恢复的因果关系
2. **干预研究**：测试菌群定向治疗（益生菌、FMT、膳食干预）的效果
3. **机制研究**：深入研究 tnaA 基因与吲哛产生的信号通路
4. **临床应用**：开发微生物生物标志物用于患者分层和个性化治疗

## 关联连接

- [[Quiescent_Crohns_Disease]] — 其主要研究课题
- [[Tryptophan_Metabolism]] — 色氨酸代谢的发现者
- [[Sulfur_Metabolism]] — 硫代谢异常的阐述者
- [[SPARC_IBD]] — 主要参与的研究队列
- [[摘要-quiescent-crohns-sulfur-tryptophan]] — 其代表作的摘要
- [[University_of_Michigan_Medical_School]] — 工作机构
- [[geneshot]] — 开发的生物信息学工具

## 论文与著作

### 第一作者或通讯作者（核心论文）
1. **Golob et al.** (2024) "The Microbiome in Quiescent Crohn's Disease..." — Gastro Hep Advances

### 相关方法论发表
- geneshot 流程的方法学论文（详见 GitHub）

## 联系与资源

- **机构**：University of Michigan Medical School
- **代码库**：GitHub（Golob-Minot）
- **数据获取**：IBD Plexus (https://www.crohnscolitisfoundation.org/research/grants-fellowships/ibd-plexus)
