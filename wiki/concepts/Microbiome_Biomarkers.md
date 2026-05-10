---
title: "Microbiome Biomarkers"
type: concept
tags: [生物标志物, 诊断, 微生物组, 精准医学]
sources: [Clippings/Noninvasive, microbiome-based diagnosis of inflammatory bowel disease.md]
last_updated: 2026-04-28
---

## 定义

微生物组生物标志物 (Microbiome Biomarkers) 是指特定的微生物群落组成、特定菌种的丰度及其代谢产物，用于**疾病诊断、预测或监测**的生物学指标。与单一生物标志物相比，**多菌株生物标志物面板**通过整合多个菌种的信息，显著提高了诊断准确性和稳定性。

## 微生物组生物标志物的优势

### 非侵入性
- **样本采集简单**：基于粪便样本，无需内镜或其他侵入性检查
- **患者易接纳**：便于大规模筛查和纵向监测
- **成本效益**：相比内镜检查成本较低

### 诊断准确性
- **优于传统生物标志物**：多菌株面板的诊断性能优于粪钙卫蛋白
  - UC 诊断：AUC 0.85 vs 0.81 (粪钙卫蛋白)
  - CD 诊断：AUC 0.87 vs 0.79 (粪钙卫蛋白)
- **跨越多重验证**：在不同地理位置、种族人群中保持高度一致的诊断性能

### 病理反映性
- **反映潜在病理过程**：不仅反映炎症状态，还反映微生物群落的功能性异常
- **无症状疾病识别**：即使在无症状 (inactive) 疾病中也能维持诊断能力
- **治疗独立性**：诊断性能与 IBD 治疗状态无关，适用于广泛临床场景

## IBD 特异性生物标志物

### UC 生物标志物（10 种菌）

**核心判别菌（顶级特征）：**
1. *Fusicatenibacter saccharivorans* — 最重要的耗尽菌
2. *Clostridium leptum* — 产短链脂肪酸，重要保护菌
3. *Gemmiger formicilis* — 产短链脂肪酸，代谢活跃

**其他关键生物标志物：**
- 富集：*Gemella morbillorum*、*Blautia hansenii*、*Actinomyces* sp. 181、*Clostridium spiroforme*
- 耗尽：*Ruminococcus torques*、*Odoribacter splanchnicus*、*Bilophila wadsworthia*

### CD 生物标志物（9 种菌）

**核心判别菌（顶级特征）：**
1. *Blautia obeum* — 最重要的耗尽菌，产短链脂肪酸
2. *Lawsonibacter asaccharolyticus* — 耗尽菌，保护性角色
3. *Roseburia inulinivorans* — 耗尽菌，产短链脂肪酸
4. *Actinomyces* sp. oral taxon 181 — 富集菌，新发现
5. *Escherichia coli* — 富集菌，粘附侵袭性

**其他关键生物标志物：**
- 富集：*Bacteroides fragilis*（产毒素）
- 耗尽：*Roseburia intestinalis*、*Dorea formicigenerans*、*Eubacterium* sp. CAG: 274

## 诊断模型性能

### 发现队列（发展阶段）
- **UC 模型**：AUC 0.95、敏感性 88%、特异性 81%
- **CD 模型**：AUC 0.95、敏感性 88%、特异性 89%

### 多队列验证（跨越 8 个人群）
- **UC 模型**：AUC 0.81-0.87 (平均 0.82)
- **CD 模型**：AUC 0.73-0.97 (平均 0.76)
- **稳定性**：地理和种族多样性下维持高诊断准确性

### 非 IBD 疾病特异性
- **UC vs 非 IBD 疾病**：AUC 0.78 (包括 CRC、IBS、肥胖等)
- **CD vs 非 IBD 疾病**：AUC 0.72
- **特异性菌**：如 *Ruminococcus torques* 耗尽和 *Clostridium spiroforme* 富集仅在 UC 中出现

## 技术实现

### 检测方法
1. **宏基因组测序** (Metagenomic Sequencing)：研究用途
2. **多重液滴数字 PCR** (m-ddPCR)：临床应用，靶向特定菌种

### 模型算法
- **随机森林算法** (Random Forest)：用于诊断模型构建
- **主坐标分析** (PCoA)：菌群结构可视化
- **差异丰度分析** (MaAsLin2)：鉴定显著差异菌

## 临床应用前景

- **无创筛查**：作为 IBD 初级筛查工具
- **诊断辅助**：补充内镜检查
- **治疗监测**：跟踪治疗效果和疾病活动性
- **精准医学**：结合患者个体化菌群谱进行精准治疗

## 关联连接

- [[摘要-mitarget-ibd-research]] — miTarget IBD 研究计划

- [[Inflammatory_Bowel_Disease]] — 主要应用场景
- [[Ulcerative_Colitis]] — UC 诊断应用
- [[Crohn_Disease]] — CD 诊断应用
- [[Dysbiosis]] — 基础概念
- [[Metagenomic_Sequencing]] — 关键检测技术
- [[Short_Chain_Fatty_Acids]] — 相关代谢产物
- [[摘要-microbiome-based-ibd-diagnosis]] — 相关研究
