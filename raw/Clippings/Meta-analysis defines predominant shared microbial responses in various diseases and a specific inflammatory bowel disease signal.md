---
title: "Meta-analysis defines predominant shared microbial responses in various diseases and a specific inflammatory bowel disease signal"
source: "https://link.springer.com/article/10.1186/s13059-022-02637-7"
author:
  - "[[Haya Abbas-Egbariya]]"
  - "[[Yael Haberman]]"
  - "[[Tzipi Braun]]"
  - "[[Rotem Hadar]]"
  - "[[Lee Denson]]"
  - "[[Ohad Gal-Mor]]"
  - "[[Amnon Amir]]"
published: 2022-02-23
created: 2026-05-02
description: "Gut microbial alteration is implicated in inflammatory bowel disease but is noted in other diseases. Systematic comparison to define similarities and speci"
tags:
  - "clippings"
---
## Abstract

### Background

Gut microbial alteration is implicated in inflammatory bowel disease but is noted in other diseases. Systematic comparison to define similarities and specificities is hampered since most studies focus on a single disease.

### Results

We develop a pipeline to compare between disease cohorts starting from the raw V4 16S amplicon sequence variants. Including 12,838 subjects, from 59 disease cohorts, we demonstrate a predominant shared signature across diseases, indicating a common bacterial response to different diseases. We show that classifiers trained on one disease cohort predict relatively well other diseases due to this shared signal, and hence, caution should be taken when using such classifiers in real-world scenarios, where diseases are intermixed. Based on this common signature across a large array of diseases, we develop a universal dysbiosis index that successfully differentiates between cases and controls across various diseases and can be used for prioritizing fecal donors and samples with lower disease probability. Finally, we identify a set of IBD-specific bacteria, which can direct mechanistic studies and design of IBD-specific microbial interventions.

### Conclusions

A robust non-specific general response of the gut microbiome is detected in a large array of diseases. Disease classifiers may confuse between different diseases due to this shared microbial response. Our universal dysbiosis index can be used as a tool to prioritize fecal samples and donors. Finally, the IBD-specific taxa may indicate a more direct association to gut inflammation and disease pathogenesis, and those can be further used as biomarkers and as future targets for interventions.

## Introduction

Gut microbial imbalance is noted in inflammatory bowel diseases (IBD) \[[^1],[^2],[^3]\]. However, studies spanning different countries failed to report consistent unified microbial alterations \[[^4]\], and while altered microbiome likely plays a role in IBD pathogenesis, the precise microbial dysfunction is not entirely understood. In parallel, many other disease-control studies, most of which are not linked with chronic gut inflammation, have shown alteration in the gut microbial composition. Those various microbial shifts across diseases emphasize the lack of systematic understanding regarding the role of the gut microbiota in healthy and disease states, and its link with the overt gut inflammation seen in IBD. Specifically, we still lack a comprehensive understanding whether different diseases like IBD are characterized by distinct microbial shifts that may be therapeutically targeted or rather by a non-specific general “sick-microbial” state \[[^5]\].

We re-analyzed raw data from publicly available V4 16S amplicon sequences using a unified pipeline (28 diseases, 59 disease cohorts, and 12,838 subjects). We defined 731 bacterial amplicon sequence variants (ASVs) that were associated with a disease state in at least one disease cohort, and by examining the behavior of these ASVs across all disease cohorts, we identified a robust nonspecific microbial response shared by many diseases. Random forest disease-classifiers trained on one disease cohort (i.e., IBD) also predicted relatively well the disease state in other cohorts with different diseases, likely due to this shared microbial pattern, and we used it to define a novel universal dysbiosis index (UniDI) that successfully differentiates between most cases and controls across diseases. Finally, we identified a set of UC/CD-specific taxa that show a pronounced change in UC/CD compared to other diseases. Those can be prioritized for laboratory exploration to study their potential role in eliciting the intestinal inflammation seen in IBD and can direct future IBD-specific interventions.

## Results

### Uniform case-control analytic pipeline

We identified 59 case-control studies that used V4 16S rRNA amplicon sequencing spanning 28 diseases and 12,838 subjects from different geographical regions including North America, Europe, Middle East, and Asia (Table [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#Tab1), Additional file [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM1): Table S1). Raw reads from all samples were trimmed and denoised using Deblur. We included two large studies with multiple diseases: the UK Twins and the American Gut Project (AGP) cohorts. In those and other studies where several diseases were investigated, samples were split to specific disease cohorts, with controls randomly divided between the different disease cohorts and using only one sample per patient. Since all cohorts used the same V4 16S rRNA region, we were able to process, combine, and analyze all cohorts together at the ASV sequence level, thus leading to an enhanced phylogenetic resolution compared to taxonomy-based comparisons, which are usually limited to the genus level for 16S amplicon sequencing. Study-specific variation was a major confounder (Additional file [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM1): Fig. S1A), likely due to sample collection, processing methods \[[^36]\], and differences in the populations studied. This was further supported by measuring distances (beta-diversity) between sample-groups within and between studies (Additional file [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM1): Fig. S1B), showing significantly higher distances between studies.

**Table 1 Description of case control comparison included in our analyses**

To overcome these study-specific signals and facilitate comparison across disease cohorts, we devised a per-study effect size-based pipeline (Fig. [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig1)). The concept is to calculate the case/control effect-size for each ASV within each disease cohort separately, and then perform the meta-analysis on these effect-sizes rather than on the ASV frequencies. Specifically, we first identified ASVs showing a potential case/control difference in at least one study. Since this initial screening is used to identify ASVs that are then further selected using additional statistical tests, and in order to prevent bias in ASV identification due to different cohort sizes, we selected a small subset of samples per study, with a high FDR (dsFDR< 0.25 \[[^37]\]), in order to include as many studies and differentially abundant ASVs as possible (Fig. [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig1)). Seven hundred thirty-one bacterial ASVs showing significant disease association in at least one cohort were combined (Fig. [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig1) heatmap), and the effect size \[labeled herein as normalized rank mean difference (NRMD)\] was now calculated between cases and controls within each disease cohort, using all samples in each disease cohort (*n* = 12,838).

**Fig. 1**

![Fig. 1](https://media.springernature.com/lw685/springer-static/image/art%3A10.1186%2Fs13059-022-02637-7/MediaObjects/13059_2022_2637_Fig1_HTML.png?as=webp)

[Full size image](https://link.springer.com/article/10.1186/s13059-022-02637-7/figures/1)

Meta-analysis pipeline. We reanalyzed 12,838 human gut samples, spanning 59 disease cohorts linked with 28 unique diseases (**A**). Per-sample V4 16S amplicon sequencing raw reads were processed using Deblur, resulting in bacterial amplicon sequence variants (ASVs) (**B**). Potential disease dependent ASVs within each original study were identified separately within each disease cohort (rank mean tests, FDR < 0.25, using a random subset of 23 cases and 10 controls to include as many case/control comparison and avoid dominance of large cohort size) (**C**). ASVs were then combined, resulting in 731 unique ASVs (**D**). For each disease cohort, the effect size (normalized rank mean difference—NRMD) was calculated for these 731 ASVs using all available samples in each cohort (*n* = 12,838) (**E**), and results were combined to a single table (**F**). Each column in the heatmap represents a single disease cohort, and each row represents a single ASV, with color representing the NRMD effect size; red and blue colors indicate higher or lower in disease respectively, while white indicates ASVs not present in the disease cohort. Non-disease specific ASVs were identified using a binomial test (FDR < 0.1) (**G**), whereas CD/UC specific ASVs were identified using rank-mean test (FDR < 0.1) (**H**)

### Similarities and differences in the microbial composition within and between disease states

To evaluate the ability of our pipeline to reduce the study specific contribution and to capture signals across diseases/studies, we used a Bray-Curtis based principal coordinates analysis (PCoA) either on the original mean ASVs relative abundance in cases and controls in each study (Additional file [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM1): Fig. S1C-D) or on the NRMD effect size resulting from our pipeline. Using the original mean relative abundance, cases, and controls from each disease cohort tended to be positioned together (Additional file [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM1): Fig. S1C). In contrast, when using the effect size (NRMD) based distances, we were able to eliminate much of the cohort specific signal, with the signal from the different cohorts being spread-out (Additional file [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM1): Fig. S1D). The full NRMD-based distance matrix (Fig. [2](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig2) A) shows clustering according to disease rather than study. For example, three Parkinson studies from 3 different cohorts (2 from the US and 1 from Europe) showed high similarities with each other (Fig. [2](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig2) A). IBD studies were significantly enriched in the left main dendrogram branch (chi-squares *p* value = 0.009, 11/28 vs. 3/30), and CD and UC disease cohorts seemed to intermix. However, 17 other disease cohorts including Alzheimer, lupus, and autism also clustered on the left dendrogram branch. Coloring of the NRMD-based PCoA by country of origin or disease shows that cohorts from the same geographic region are spread through the graph (Fig. [2](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig2) B) and that different IBD cohorts or different Parkinson cohorts cluster together by disease type (Fig. [2](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig2) C).

**Fig. 2**

![Fig. 2](https://media.springernature.com/lw685/springer-static/image/art%3A10.1186%2Fs13059-022-02637-7/MediaObjects/13059_2022_2637_Fig2_HTML.png?as=webp)

[Full size image](https://link.springer.com/article/10.1186/s13059-022-02637-7/figures/2)

Similarities and differences in the microbial composition between diseases. Modified Bray-Curtis distance matrix was calculated using the 731 ASV effect size ratios between cases and controls across the different disease cohorts using all samples (*n* = 12,838). Comparisons were performed between two disease cohorts only on ASVs found in both. This modified Bray-Curtis metric was used to build the distance matrix (**A**). Darker color indicates high similarity and bright color indicates low similarity. Bar colors on *X* and *Y* axes indicate the specific disease of each disease cohort, as indicated in the disease key. CD UC and IBD are all colored in dark-red but the labeling specifically indicates the disease type; however, those tend to intermix. IBD represent studies in which patients were only labeled as IBD rather than CD or UC. This matrix was then used for the generation of a principal coordinate analysis (PCoA) depicting disease cohort similarity (**B**, **C**), where disease cohorts are colored by country (**B**) or specific disease (**C**)

### Non-specific microbial alteration associated with multiple pathologies

To define those non-specific general changes, we searched for ASVs whose NRMD effect size direction significantly differed from a 0.5/0.5 binomial distribution. This resulted in 128 ASVs that have similar behavior across multiple diseases (two sided binomial test with dsFDR< 0.1, Fig. [3](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig3) A) and therefore associated with general disease state. Most (97 ASVs) showed reduced abundance, while only 31 showed higher abundance across different diseases (Fig. [3](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig3) A and Additional file [2](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM2): Dataset S1). Specifically, we use the direction of the effect (rather than the effect size) for the binomial test used to identify the non-specific bacteria and therefore give equal weight to all studies not depending on the amplification level of the bacteria within each study. The relative taxonomy composition of the two groups showed that *Bacteroidetes* comprise 11 of the 97 nonspecific health-associated ASVs, whereas none were within the 31 disease-associated ASVs (chi-square *p* = 0.01, Fig. [3](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig3) B). In contrast, *Actinobacteria* taxa (chi-square *p* = 0.02) were more abundant within disease associated ASVs (3/31) compared to health-associated ASVs (1/97) (Fig. [3](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig3) B). *Lactobacillales* order (phylum: *Firmicutes*) were also significantly enriched within the disease-associated ASVs (5/31 vs. 0/97 for disease- and health-associated ASVs respectively, chi-square *p* < 0.001). To validate the use of the NRMD effect size calculation approach, we reanalyzed the same studies using two additional approaches: (i) rarifying each sample across all studies to 4000 reads/sample (Additional file [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM1): Fig. S2A, Additional file [2](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM2): dataset S1) and (ii) using the LEFSE \[[^38]\] LDA score instead of the NRMD (Additional file [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM1): Fig. S2B and Additional file [2](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM2): Dataset S1). Those present similar results compared to the NRMD approach, with the mean effect size (i.e., higher, or lower in disease) showing similar direction for 31/31 of the disease-associated and 96/97 health-associated bacteria using the rarified data and 30/31 of the disease-associated and 95/97 health-associated bacteria using the LEFSE LDA score (see supplementary methods for details).

**Fig. 3**

![Fig. 3](https://media.springernature.com/lw685/springer-static/image/art%3A10.1186%2Fs13059-022-02637-7/MediaObjects/13059_2022_2637_Fig3_HTML.png?as=webp)

[Full size image](https://link.springer.com/article/10.1186/s13059-022-02637-7/figures/3)

Non-specific microbial signal shared across diseases. **A** Heatmap showing 128 non-specific ASVs identified by applying a binomial test on the ratios of the 731 ASVs across all diseases (FDR < 0.1). Columns are disease cohorts, and rows represent the non-specific ASVs that were significantly changed in at least four different diseases, with colors representing the NRMD. Red and blue indicate higher or lower abundance in disease respectively, while white indicates ASVs not present in the study. **B** Non-specific ASVs were separated to two groups; those lower in disease (76% of non-specific ASVs, left column), and those that are higher in disease (24% of non-specific ASVs, right column). The fraction of bacteria from each of these groups is shown for three taxonomic levels as indicated: phylum, order, and class

To infer microbial functions enriched in the health vs. disease-associated ASV bacteria, we applied Picrust2 \[[^39]\] and identified 10 KEGG functions that were more common in disease, and 14 more common in controls (rank-mean test with dsFDR < 0.1, Additional file [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM1): Fig. S3 and Additional file [3](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM3): Dataset S2). Functions enriched in disease associated ASVs included carbohydrate metabolism, whereas functions enriched in health associated ASVs included metabolism of cofactors and vitamins, and amino acid metabolism. Interestingly, cellular community pathways and more specifically quorum sensing genes, were more common in disease associated ASVs process allowing bacterial populations to communicate and coordinate group behavior, a process which is more commonly used by pathogens \[[^40]\].

### IBD-specific microbial alteration is predominantly linked to increased abundance of individual taxa

We next searched for ASVs specifically associated with CD/UC. For that, the naïve approach of performing differential abundance on CD/UC samples compared to controls without considering the behavior in other disease cohorts does not suffice. We therefore defined CD/UC-specific ASVs as ASVs showing significantly higher or lower NRMD effect size in fecal samples from CD and UC disease cohorts (*n* = 10) compared to other non-IBD disease cohorts (*n* = 45) (using permutation-based rank mean test of the per-disease cohort NRMDs, with dsFDR = 0.1). Fifteen ASVs were significantly related to UC and CD, with 13 showing a higher NRMD between UC and CD cases and controls and 2 showing a decrease in NRMD between UC/CD and controls (Fig. [4](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig4) A and Additional file [4](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM4): Dataset S3). Those specific CD and UC enriched ASVs included taxa from *Gemellaceae*, *Veillonellaceae*, *Fusobacteriaceae*, and *Streptococcaceae* families. Term enrichments of those 13 CD/UC-associated specific ASVs using dbBact database showed enrichment for microbial taxa seen in saliva samples (Fig. [4](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig4) B), with more significant overlap with salivary samples in 2 additional studies (Fig. [4](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig4) C). Attempts to find other disease-specific signals, including for Parkinson’s disease failed, likely due to lack of sufficient number of studies linked with a specific condition.

**Fig. 4**

![Fig. 4](https://media.springernature.com/lw685/springer-static/image/art%3A10.1186%2Fs13059-022-02637-7/MediaObjects/13059_2022_2637_Fig4_HTML.png?as=webp)

[Full size image](https://link.springer.com/article/10.1186/s13059-022-02637-7/figures/4)

Salivary bacteria are enriched in samples from Ulcerative colitis and Crohn’s disease. **A** Heat map showing 15 CD/UC “specific” ASVs with significantly higher (or lower) effect size in fecal samples of CD and UC cases compared to controls in comparison to other disease cohorts \[rank-mean test on the NRMD effect sizes in 10 fecal CD and UC studies compared to other disease (*n* = 45)\]. Columns are disease cohorts, and rows represent the CD/UC specific ASVs with colors representing the NRMD; red indicates higher abundance and blue indicates lower abundance in cases vs. controls, and white indicates ASVs not present in the study. **B** A word cloud was generated using dbBact ([http://dbbact.org/](http://dbbact.org/)) \[[^41]\] using the increased UC/CD-specific bacteria, indicating that UC/CD-specific increased bacteria has been previously found in fecal and saliva human samples. **C** Venn diagram showing overlap between the 31 increased non-specific ASVs and 13 IBD-specific ASVs (red and green circles respectively) salivary obtained samples including those ASVs that are present 25% and above of the samples (blue) identified from other cohorts \[AGP (left) and PRJNA38386 \[[^42]\] (right) see methods section for additional details\], emphasizing significant larger overlap between the IBD-specific ASVs and salivary ASVs (chi-square *p* < 0.05) in contrast to the disease non-specific increased ASVs

### Inaccuracy of classifier to differentiate between different disease states

Machine learning classifiers are commonly used to differentiate between healthy and disease cases \[[^43]\]. However, the fact that a large set of bacteria display a consistent change across multiple disease raises the concern that classifiers may capture this shared signal, which may lead to incorrect disease identification and the inability to differentiate between diseases. To test this, we used a supervised learning Random Forests (RF) classifier. For each disease cohort, we separately trained RF to differentiate cases/controls for this disease cohort and then tested its ability to differentiate cases/controls on a different disease cohort. AUC performances are shown in Fig. [5](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig5) A, where each row represents a disease cohort on which a classifier was trained, and columns represent the disease cohort on which the classifier was tested (when the training and test cohorts were the same, samples were split 2:1 for training/validation). As an estimate for the inherent noise present in the classifier performance, we also tested the performance of the same procedure where the case/control labels of each testing disease cohort were randomly shuffled (Fig. [5](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig5) B and Additional file [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM1): Fig. S4). Predicting case/control state in UC and CD by using models built upon other UC and CD cohorts worked relatively well and mostly above what is expected by random. However, models built on other diseases also predicted CD and UC relatively well, and vice-versa, models built on CD and UC were able to predict other diseases. Those results indicate that disease classifiers perform well in identifying sick vs. healthy states but may fail to differentiate between different diseases.

**Fig. 5**

![Fig. 5](https://media.springernature.com/lw685/springer-static/image/art%3A10.1186%2Fs13059-022-02637-7/MediaObjects/13059_2022_2637_Fig5_HTML.png?as=webp)

[Full size image](https://link.springer.com/article/10.1186/s13059-022-02637-7/figures/5)

Disease classifier and dysbiosis index predict general microbial signal rather than disease specific signals. **A** Random Forest classifier heatmap, showing the disease/control prediction AUC in each disease cohorts (columns) based on training the classifier on datasets in the different rows (see methods for details). Blue indicates high prediction AUC (> 0.5) and red indicates AUC < 0.5. Training and prediction in each comparison were performed only on shared ASVs between the trained and the predicted cohorts. Squares marked in the heatmap, indicate the prediction results obtained after training of the classifier using the same cohort. **B** Random Forest classifier heatmap, showing the prediction AUC after performing random permutation of labels of the predicting cohort prior to the classifier prediction, to further validate the non-random results obtained in **A**. **C** Dysbiosis index per dataset was measured by two models: per-sample rank (UniDI) \[[^5]\], and by using the CD dysbiosis index \[[^2]\], and the resulting *P* -value (Mann-Whitney) after comparing disease and controls for each dataset is shown in the plot where the *x* -axis showing the sample-rank model (UniDI), and the *y* -axis showing the CD dysbiosis index \[[^2]\]. For the performance evaluation, we used a leave-one-out approach. We iterated over all disease cohorts, and for each iteration, the analysis was performed while leaving out a single validation disease cohort. The *up*  \_  *nonspecific*, *down*  \_  *nonspecific* ASV groups were identified as described but without the validation cohort (i.e., the non-specific ASVs were identified based on 58 disease cohorts). Diseases with at least 2 cohorts were colored by a specific color, while single cohorts were all colored in gray (detailed map in Additional file [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM1): Fig. S5). Pink left down quadrant indicates non-significant *p* -value (p > 0.05) using both UniDI and CD dysbiosis index, green left upper quadrant indicates significant *p* -value (*p* < 0.05) only using CD dysbiosis index, the purple right down quadrant indicates significant *p* -value (*p* < 0.05) only using UniDI, while the larger white quadrant indicates significant *p* -values in both UniDI and CD dysbiosis index. All dot under the diagonal line received lower p value with UniDI while those above had a lower p value with the CD dysbiosis index

### Universal dysbiosis index (UniDI)

A universal dysbiosis index (UniDI) was built on the identified 128 non-specific ASVs signal. We calculated the per-sample UniDI by rank-transforming the bacteria and computed the normalized log ratio of the sum of the ranks of the 97 health-associated and 31 disease-associated ASVs. We then compared the UniDI (using a leave-one-out approach) to a previously published taxonomy-based CD dysbiosis index \[[^2]\]. For the performance evaluation, we used a leave-one-out approach: we iterated over all disease cohorts, and for each iteration performed the analysis while leaving out a single validation disease cohort. The *up*  \_  *nonspecific*, *down*  \_  *nonspecific* ASV groups were identified as described above (see the “Identification of shared (“non-specific”) ASVs” section), but without the validation cohort (i.e., the non-specific ASVs were identified based on 58 disease cohorts). The resulting UniDI performed better than the CD dysbiosis index, indicating that UniDI can successfully differentiate between most cases and controls across a wide variety of diseases (Fig. [5](https://link.springer.com/article/10.1186/s13059-022-02637-7#Fig5) C, Additional file [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM1): Fig. S5, and Additional file [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM1): Fig. S6). Among the UC/CD studies, UniDI showed more significant changes between cases and controls (10/14 studies) than CD dysbiosis index (7/14). Similar results were shown in other diseases such as Parkinson’s; UniDI succeeded to show significant changes in dysbiosis index in 2 out of 3 studies included in the meta-analysis, in comparison to 0 out of 3 in the CD dysbiosis index. These results indicate that UniDI can successfully differentiate between most cases and controls across a wide variety of diseases.

## Discussion

Our meta-analysis used a novel standardized pipeline starting from per-sample raw reads, across diverse pathologic conditions, different parts of the world, 28 diseases, and 12,838 subjects. We focused on studies that used the V4 regions, to facilitate comparison at the ASVs level rather than taxonomy and calculated the per ASV effect size between cases and controls within each original cohort, thus minimizing the study-specific signature. We identified a robust non-specific general disease response dominated by reduction of microbial ASVs (97 ASVs), with a smaller group of 31 bacterial ASVs being over-represented in disease. These non-specific microbial changes may reflect a general response of the body to pathologic conditions and therefore are less likely to be the main source of the chronic gut inflammation seen in IBD. Disease classifiers performed well in identifying many sick vs. healthy states, likely due to this general signal. We define a novel universal dysbiosis index (UniDI) utilizing the shared disease-associated ASVs, that can successfully differentiate between most cases and controls across a wide variety of diseases. Finally, we identified a set of IBD-specific taxa (most of which are salivary bacteria \[[^2]\], with an increased abundance in IBD), potentially implying a more direct causal association between those and IBD pathogenesis and gut inflammation. Interestingly, recent studies showed that ectopic displacement of oral bacteria in the gut environment resulted in dysbiosis and a decrease in Th17 cells and fecal IgA levels and an increase in the M1/M2 macrophage ratio, thereby promoting chronic inflammation \[[^44]\].

Meta-analyses systematically compare several independent studies to capture consistent and specific signals across diseases, cohorts, populations, and protocols. The basic unit is the disease cohort rather than samples. Microbiome meta-analysis can take place at several levels; systemic review comparing the results without reanalyzing the raw data \[[^4]\], reanalyzing the raw data but not focusing on a specific sequence, enabling only comparisons at the taxonomy level \[[^5], [^45]\], and lastly reanalyzing the raw data and focusing on a specific sequence that enables direct comparison within each cohort as performed here. Microbiome-related meta-analyses have already suggested some inconsistencies in bacterial signals in IBD \[[^4], [^5], [^36]\]. A thorough systematic review \[[^4]\] of published results compared 45 articles noted that increase in *Enterobacteriaceae taxa* and a decrease in the butyrate producing *Faecalibacterium prausnitzii* seem to be consistent across studies. Our analyses imply that decrease in *Faecalibacterium prausnitzii* is seen across multiple diseases and are likely not IBD-specific. Another landmark meta-analysis study took the second approach \[[^5]\], started from the raw data of 28 published case-control studies, that sequenced different regions on the 16S gene (not limited to the V4 region), and also highlighted the depletion of health-associated bacteria across multiple diseases, and some specific microbial signal in colon cancer but not in IBD. We took the third approach, limiting the analyses to similar sequencing region of the 16S (V4). This reduces the number of available studies, but it enables ASV rather than taxonomy-based comparison. For example, 2 different *Clostridium* ASVs showed opposite direction of change (SV14256 increased and SV12376 decreased, Dataset S1) and a similarly opposite pattern was noted for 2 *Ruminococcus* ASVs (SV14506 and SV08112). The non-specific health-associated taxa included *Faecalibacterium prausnitzii* and *Coprococcus* (family: *Lachnospiraceae*) ASVs. In contrast to previous studies, we highlight also ASVs that are induced (rather than only reduced) as part of the non-specific signal including *Clostridium XlVa* (known as *Enterocloster*), *Lactobacillus salivarius*, and *Rothia (family: Micrococcaceae)*. Similarly, a recent meta-analysis of microbiome gene functions of nearly 2000 publicly available fecal metagenomic samples of 7 different diseases also identified many functions that were linked to and overlapped with multiple diseases \[[^46]\].

Disease-specific microbial ASVs may suggest a more direct link to pathogenesis, and those can be used as biomarkers for diagnostics and for design of potential future interventions. We identified 13 UC/CD-specific ASVs bacteria that were more increased in IBD compared to other diseases. Those included taxa from *Gemellaceae*, *Dialister (*family: *Veillonellaceae), Blautia producta* (family: *Lachnospiraceae*), and *Streptococcus* (family: *Streptococcaceae*). *Gemellaceae* taxa were previously linked with the risk for future CD flare \[[^1]\]. Additionally, in cystic fibrosis, *Gemella* was also increased during exacerbation and was found to be the most discriminative genus between baseline and exacerbation samples \[[^47]\]. Similarly, presence of *Streptococcus* in stool samples before CD surgery is predictive of future CD recurrence based on endoscopic scores 6 months after surgery \[[^48]\]. *Streptococcus* and *Veillonella* can interact metabolically, co-occur in ecosystems, and co-aggregate in biofilms \[[^49]\], and their combined incubation results in higher IL8 cytokines secretions from dendritic cells \[[^50]\]. Two of the UC/CD specific ASVs (*Clostridium perfringens* and *Ruminococcus gnavus*) were also part of non-specific signals but those showed significant increase in CD and UC. Those taxa were shown to be specifically reduced during antibiotic treatment in pouchitis IBD patients who responded to treatment, further indicating potential causal associations between those taxa and gut inflammation \[[^51]\]. Interestingly, many of those IBD-specific bacteria were shown to be present in saliva samples. This may be due to the lower bacterial biomass observed in IBD feces \[[^2], [^52], [^53]\], thus leading to an increased fraction of bacteria present in swallowed saliva, or that some of these oral bacteria affect the gut immune response. Further studies are required to clarify these questions.

Disease classifiers are frequently used to identify patients with a given disease. However, since most focus on a single disease and a group of healthy controls, the presence of a strong disease non-specific bacterial response may influence the performance if used outside of the original study in diverse population with different diseases. Our results show that a classifier trained on IBD disease cohort classified with relatively good performance disease/control states in lupus, schizophrenia, or Parkinson’s. This raises the concern that such classifier can incorrectly classify patients with other unrelated disease as cases of the disease of interest. Notably, our results do not preclude the possibility of classifiers to differentiate between different diseases when trained on datasets containing multiple diseases, but rather that it is recommended to train those classifiers also on a large set of diseases.

The concept of a dysbiosis index for estimation of the general host dysbiosis or healthy state was suggested in the landmark IBD study \[[^2]\] and in recent shotgun sequencing dataset \[[^54]\]. The recent shotgun sequencing dataset used 4347 human stool metagenomes from 34 published studies across healthy and 12 different disease conditions highlighting 50 bacterial species more prevalent in pooling data from healthy vs. nonhealthy state cases. Once generated, this index can be applied on other shotgun datasets. We expanded this idea using 12,838 subjects, 59 disease cohorts, and 28 diseases, and we generated an index that can be applied to dataset generated using 16S sequencing. We note that an advantage of shotgun compared to 16S sequencing is that shotgun dataset can also inform regarding metabolic pathways and functions, which can be an interesting future approach for to define healthy vs. nonhealthy state pathways across diseases. Our UniDI is shown to perform better than the CD dysbiosis index \[[^2]\] indicating that UniDI can successfully differentiate between most cases and controls across a wide variety of diseases. One possible use for UniDI is its application as an additional tool for prioritizing fecal microbiota transplant (FMT) donors, where it is desired to obtain samples from donors with lower disease probability. Another application as already suggested \[[^54]\] for such index is for providing insight into one’s health status from a gut microbiome and for inferring the likelihood of disease independent of the clinical diagnosis. In addition, this index can be calculated per samples and can be included in gut microbial personal report, which can also be followed longitudinally for variations linked with diet and environmental modification in clinical studies.

Our work has several strengths, we included 12,838 subjects, 59 disease cohorts, and 28 diseases from around the world, and the results can be generalizable to those regions. By analyzing only studies covering the V4 region, combined with a unified denoising approach, we combined the different studies at the ASV rather than taxonomic assignments, which are typically limited to the genus level for amplicon sequencing. Additionally, by calculating the within-study disease effect, and using these effect sizes rather than the per-sample abundances, we were able to mitigate biases originating from the different cohorts and experimental methods. Limitations include the need to have controls in each study to capture the effect size, the inability to capture variations between controls, and that it is unlikely but possible that the controls in one cohort have the disease in another cohort. Nevertheless, the grouping of IBD and Parkinson’s disease cohorts from several cohorts using the effect size pipeline is reassuring, and in some of the larger cohort, controls were randomly divided between disease cohorts. Other limitations include the limited metadata characteristics across cohorts and the use of 16S rRNA amplicon sequencing (rather than shotgun data) which limits the ability to identify taxonomy up to the strain levels and the bacteria associated metabolic pathways and functions. All studies selected were based on the same region (V4), which limits the number of available studies. We included a single sample per subject and no longitudinal data, and there may be variations in microbial population overtime that are not captured \[[^52]\]. However, we and others have shown persistent dysbiosis also in CD and UC patients in remission \[[^1], [^55]\]. While we were able to capture IBD-specific bacteria, using the same approach to identify other disease-specific signals failed, likely due to lack of sufficient studies linked with other diseases. Future analysis will require more disease-specific studies and increased data sharing, as well as additional large population-based studies like UK Twins and the American Gut Project (AGP).

## Conclusions

Despite numerous studies linking the microbiome to human health and disease conditions, there are many gaps regarding which and how those bacteria contribute to specific human disorders. In this meta-analysis, we identified a robust non-specific general response dominated by reduction of microbial ASVs with a smaller group of bacteria that were up-regulated in a large array of diseases. Those non-specific taxa can define a novel universal dysbiosis index (UniDI) that can successfully differentiate between most cases and controls across a wide variety of diseases. Finally, we identified mainly increased IBD-specific taxa, potentially indicating a more direct causal association to pathogenesis and gut inflammation, that can be used as biomarkers and potential future targets for interventions.

## Methods

### Study search and disease cohort selection strategy

We searched for case–control (disease cohort) 16S amplicon sequencing studies using specific keywords in Google Scholar and dbBact ([http://dbbact.org/](http://dbbact.org/)) and by following references in meta-analyses and related case–control studies. Only studies with at least 20 subjects, with stool or biopsies samples that were sequenced using hypervariable V4 region, and for which the per-sample raw FASTA files were publicly available for download or obtained after a specific request, were included. Those studies and sources are summarized in Table [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#Tab1) and Supplementary Table 1. Only one sample per patient was kept in cases where several samples were obtained. In studies that had UC/CD patients, we considered each disease as a separate disease cohort and randomly divided the controls between the two case-control comparisons. In this meta-analysis, we included two large cohorts with multiple diseases: the UK Twins cohort ([https://twinsuk.ac.uk/](https://twinsuk.ac.uk/)) and the American Gut Project (AGP) cohort ([http://humanfoodproject.com/americangut/](http://humanfoodproject.com/americangut/)). In cases where controls were not defined (such as in the AGP and UK twins), we considered controls as those having BMI < 30 and not taking oral medications other than supplements and vitamins. Controls were then randomly divided (taking into account age, gender, and country of origin when applicable) between the different disease cohorts in each study, so that each control sample participated only in one disease cohort. To define obesity, subjects with BMI 30 or greater were included in the obesity group. We included only subjects with a single disease category and dropped those with two or more diseases, except for IBD patients who were also diagnosed with IBS or autoimmune disease as those may co-exist (and therefore were included in the analysis as IBD patients).

### V4 16S raw data processing

Single-end reads were left trimmed to begin at the end of the 515′F primer and right trimmed to a total length of 150 bp. Reads from each cohort were then aligned and denoised using the Deblur pipeline \[[^56], [^57]\] in qiime2 (qiime2-2019.2 \[[^58]\]) using default parameters, resulting in a per-study bacterial amplicon sequence variants (ASVs) table. Based on a previous study \[[^59]\], the AGP included 10 blooming bacteria due to sending samples via postal delivery. Those bacteria were filtered across all studies included in this analysis for consistency in order to prevent sample-storage associated bacteria, and identification of the IBD-specific and non-specific ASV was performed before and after this filtering with very consistent results for the filtered and non-filtered dataset. ASV taxonomic classification was performed using a naive Bayes fitted classifier \[[^60]\], trained on the August 2013 99% identity Greengenes database, for 150 bp long reads and the corresponding primers set as implemented in qiime2 command: qiime2 feature-classifier classify-sklearn with default parameters.

### Standard (frequency-based) analysis

#### Sample preprocessing

To mitigate the effect of different cohort sizes in different studies, 23 samples were randomly chosen from each case/control group in each disease cohort. In cases where less than 23 samples were available for the group, we used all available samples instead. This resulted in a total of 2356 samples for downstream analysis. In addition, for the aggregated analysis, for each case/control group in each disease cohort all samples (up to 23) were combined into a single aggregate sample by taking the mean frequency for each ASV.

#### PERMANOVA

Samples were rarified to a constant depth of 3000 reads per sample, and sample-sample distances were calculated using the Bray-Curtis and unweighted-unifrac metrics using qiime2. To quantify the contribution of different factors to the microbial composition, PERMANOVA was applied using the Adonis function in the R package Vegan (vegan: Community Ecology Package. R package version 2.5-6.[https://CRAN.R-project.org/package=vegan](https://cran.r-project.org/package=vegan)) \[[^61]\] using both metrics. Variables tested were as follows: case/control, specific disease, country, cohort, disease cohort, and age group (adult/child). Analysis was performed on the original samples as well as on the aggregated samples (i.e., one sample per case/control group in each disease cohort). The total variance explained by each variable was calculated independently of other variables (that is, as the sole variable in the model).

#### Quantification of cohort vs. case/control distance contribution

Bray-Curtis distances between pairs of aggregated samples were calculated for the following pairs: case and control pairs from the same disease cohort, cases from different disease cohorts, and controls from different disease cohorts. The distribution of the distances of these three groups was compared using a two-sided non-parametric Mann-Whitney test.

### Effect size \[normalized rank-mean difference (NRMD)\] based analysis

#### Selection of ASVs and calculation of the per-ASV effect size

To create the per disease cohort ASV case/control effect table, we used only ASVs that show significant differential abundance (between cases and controls) within at least one disease cohort. These ASVs were identified independently within each disease cohort using a non-parametric rank mean test as implemented in Calour \[[^62]\] with dsFDR multiple hypothesis correction \[[^37]\] (FDR < 0.25), based on a random subset of 23 cases and 10 controls samples per disease cohort, in order to avoid the dominance of disease cohorts with a large number of samples (since a larger number of samples can provide higher statistical power). A unified list of ASVs showing potential differential abundance in at least one study was then generated. For each of those ASVs, we then calculated the direction of change and the effect size \[normalized rank mean difference NRMD) between the mean of cases and controls\] in each case-control comparison using all samples in the disease cohort across all studies (to provide a better estimation of the real effect size). The per-ASV normalized rank-mean difference (NRMD) is scaled to be in the range of − 1 to 1 (independent of the number of samples in each group) and was calculated using the formula:

$$
NRMD\left(i,x\right)=\left( mean\left({G}_{case}\left(i,x\right)\right)- mean\left({G}_{control}\left(i,x\right)\right)\right)/\left(\frac{n\left({G}_{case}\left(i,x\right)\right)+n\left({G}_{control}\left(i,x\right)\right)\ }{2}\right)
$$

where *NRMD* (*i*, *x*) is the normalized effect size for ASV *x* in disease cohort *i*, *G* <sub><i>case</i></sub> (*i*, *x*), *G* <sub><i>control</i></sub> (*i*, *x*) represent the ranked frequencies of the case/control (respectively) for ASV *x* in disease cohort *i*, and *n* (*G*) represents the number of samples in group *G*.

#### NRMD-based beta diversity analysis

To quantify the similarity/dissimilarity between the different disease cohorts, we used the normalized difference between cases and controls in each disease cohort (NRMD). Since not all ASVs are present in all disease cohorts, for each pair of disease cohorts, we calculated a modified Bray-Curtis distance using only the ASVs present in both disease cohorts. The distance was calculated as follows:

$$
D\left(i,j\right)=\sum_{\begin{array}{c}x\\ {}x\ is\ in\ disease\ cohort\ i\\ {} and\\ {}x\ is\ in\ disease\ cohort\ j\end{array}}\frac{\mid NRMD\left(i,x\right)- NRMD\left(j,x\right)\mid }{\left| NRMD\left(i,x\right)\right|+\mid NRMD\left(j,x\right)\mid }
$$

where *i* and *j* denote two disease cohorts, and *D* (*i*, *j*) is the modified Bray-Curtis distance between these two disease cohorts.

This modified Bray-Curtis distance is similar to the classic Bray-Curtis distance, but calculated only on ASVs present in both samples. We opted for this modified Bray-Curtis metric to reduce the effect of the different disease cohorts (i.e., different populations/extraction protocols etc.) that can lead to the lack of observations of some ASVs in specific cohorts, therefore prohibiting the determination of the NRMD for the ASV in the specific cohort.

A distance matrix for all disease cohort pairs was calculated using this modified Bray-Curtis metric. This matrix was then used for the generation of a PCoA depicting disease cohort similarity using qiime2.

#### Identification of shared (“non-specific”) ASVs

Non-specific ASVs are expected to share the same behavior (i.e., higher in cases or lower in cases) across multiple diseases, whereas for ASVs not associated with a non-specific disease response (the null hypothesis), the direction of change (higher in cases or lower in cases) is expected to follow a 0.5/0.5 binomial distribution. We therefore tested the direction of the effect size (i.e., higher (positive NRMD) or lower (negative NRMD) in cases compared to controls for the given disease cohort) and identified for ASVs whose effect size direction significantly differed from 0.5/0.5 binomial (i.e., ASVs that are higher (or lower) in cases compared to controls in a significant number of different diseases). This was implemented by using a two-sided binomial test (*p* = 0.5) on the sign of the NRMD in the different disease cohorts (only on disease cohorts where the ASV was present), followed by Benjamini-Hochberg FDR control (FDR < 0.1). To prevent bias introduced by diseases represented in multiple disease cohorts, all disease cohorts with the same disease were aggregated to a single entry (prior to the binomial test) with the NRMD defined as the mean of the NRMD of all cohorts with the same disease. The analysis was performed only on ASVs present in at least 4 disease cohorts.

NRMD results validation using additional metrics: NRMD is calculated separately for each disease cohort, and since it is rank based, it should be relatively robust to the number of reads per sample. In order to validate the results obtained using NRMD, we additionally tested for non-specific bacteria using two additional metrics: rarified NRMD and LEFSE-based LDA \[[^38]\]. Following these additional effect size calculations, we identified the set of non-specific bacteria as described previously (see specific implementation details below). Since significance depends on the *p* -value, which is highly variable even between replicates \[[^63]\], we also compared the results of LEFSE and rarified NRMD to the basic (non-rarified) NRMD by testing how the direction of change overlap between the two methods on the bacteria identified as non-specific following initial NRMD analysis as follows: for each bacteria identified as significantly non-specific (i.e., higher/lower in multiple disease cohorts compared to healthy controls), we calculated the mean of the LEFSE LDA or rarified NRMD over all disease cohorts and tested whether this mean effect size is positive (higher in disease) or negative (lower in disease). We then counted the number of bacteria for which the basic NRMD and the rarified NRMD (or LEFSE LDA) agree on the change direction. This indicates whether the same behavior (higher or lower in disease) is replicated using the different metrics used.

#### Calculation of rarified NRMD

Prior to NRMD calculation, all samples from all disease cohorts were rarified to 4000 reads per sample. Samples with < 4000 reads were discarded. The NRMD calculation was then performed as described above.

#### Calculation of LEFSE LDA

LEFSE (1.1.01) was used to calculate the LDA for each disease cohort using the parameters -a 1 -l 0 -w 1 (no filtering based on LDA/Wilcoxon or subgroup values). The resulting per-bacteria LDA were converted to positive/negative based on the direction of the higher group (disease/healthy) and were then used for the direction overlap analysis. For the identification of LEFSE LDA based non-specific bacteria, since LEFSE does not provide FDR correction, we used a *p* -value cutoff of 0.1 (as compared to FDR = 0.25 in the NRMD-based analysis).

#### Identification of IBD-specific ASVs

IBD-specific ASVs were defined as ASVs showing significantly higher (or lower) NRMD values in CD and UC fecal disease cohorts in comparison to all other disease cohorts. These IBD-specific ASVs were identified using a rank-mean test (implemented in Calour) on the NRMD in all studies (i.e., 10 CD and UC disease cohorts, vs. 45 disease cohorts with other diseases, not including the 2 non-specific IBD diagnosis disease cohorts, and the 2 disease cohorts that used biopsies rather than fecal samples), with dsFDR correction (FDR = 0.1).

#### dbBact terms word clouds

ASVs (either specific or non-specific), that were shown to be related to a given disease, were compared to all the annotations in the dbbact database to search for ontology terms related to those ASVs (i.e., diseases, geographical locations, bacterial main niches in the body, and habitant for those bacteria). For each term, the word size is the F-score combining the precision (i.e., how many of the query sequences contain the given term) and the recall (i.e., how many of the dbBact annotations containing the term contain the query sequences). Blue and red word colors indicate terms positively or negatively associated with the query sequences respectively.

#### Identification of salivary ASVs in additional studies

Per-sample FASTA reads files were downloaded from the SRA for two studies that included salivary microbiome samples (AGP and PRJNA383868 \[[^42]\]) sequenced using the V4 region. Sequences were processed using the same pipeline described for the current dataset, and we summarized those ASVs that were present in 25% and more in the salivary samples (those 2 cohorts included 500 and above participants) and looked for overlapped with disease non-specific increased ASVs (*n* = 31) and IBD-specific increased ASVs (*n* = 13).

### Functional enrichment analysis in non-specific bacteria

Functional analysis was performed using per-ASV prediction of KEGG functions obtained using PICRUSt2 \[[^39]\]. We then searched for KEGG functions present at significantly higher (or lower) fractions in health-associated non-specific bacteria compared to disease-associated non-specific bacteria (e.g., KEGG functions more common in bacteria that increase (decrease) in multiple diseases compared to the bacteria that decrease (increase) in controls). The test was performed on the normalized per-ASV KEGG function table aggregated at KEGG level 2, using the rank-mean test (implemented in Calour) with dsFDR multiple hypothesis correction (FDR < 0.1), comparing relative abundances of KEGG functions in disease-associated vs. health-associated ASVs.

### Classifier building and performance

For the classification, each disease cohort was randomly subsampled to a maximum of 23 cases and 23 control samples. For each pair of disease cohorts (train, predict), ASVs were filtered, keeping only ASVs present in both cohorts. A random forest classifier (implemented in scikit-learn version 0.23.1, using default parameters, 100 trees per forest) was trained on the case/control samples in the training cohort. The trained classifier was then used to predict the case/control status of the prediction cohort, and false and true positive rates and AUC were calculated using scikit-learn. In the cases where the train and predict disease cohorts were the same (i.e., assessing the classifier predictions on the same disease cohort), the disease cohort samples were randomly split to 2/3 of the samples to be used as the training cohort, and the remaining 1/3 of the samples used as the prediction cohort.

Three random null-models were used: in the random-prediction model, labels of the prediction cohort (i.e., case/control) were randomly permuted prior to the classifier prediction. In the random-training model, labels of the training cohort (again case/control) were randomly permuted prior to the training (thus leaving intact the case/control differences in the prediction cohort). In the third model, labels of the prediction cohort were randomly permuted prior to the classifier prediction, and the labels of the training cohort were randomly permuted prior to the training.

AUC values shown represent the mean AUC results of 50 repeats of the entire process described (for both real data and randomizations).

### Universal dysbiosis index (UniDI)

For a given sample (containing *r* <sub><i>i</i></sub> reads for ASV 1… *n*):

$$
S=\left({r}_1,{r}_2,\dots, {r}_n\right),
$$

per-sample reads were first rank-transformed, following the method described in \[[^5]\]:

$$
\overset{\sim }{S}=\mathit{\operatorname{rank}}(S)
$$

and the dysbiosis index is then defined as the normalized log ratio of the sum of the ranks of the up and down regulated ASVs:

$$
NSDI(S)={\mathit{\log}}_2\left(\frac{\sum_{i\in up\_ nonspecific}\overset{\sim }{s_i}}{\sum_{i\in down\_ nonspecific}\overset{\sim }{s_i}}\bullet \frac{\mid down\_ nonspecific\mid }{\mid up\_ nonspecific\mid}\right)
$$

where *NSDI* (*S*) is the non-specific dysbiosis index of sample *S*, and *up*  \_  *nonspecific* and *down*  \_  *nonspecific* represent the group of disease nonspecific ASVs higher and lower in cases vs. controls respectively, as described in the paper.

The taxonomy based dysbiosis index was calculated following the method described in \[[^2]\], implemented for the denoised data using the taxonomy assigned to each ASV:

$$
DTAX(S)={\mathit{\log}}_2\left(\frac{\sum_{i\in up\_ taxonomies}{s}_i}{\sum_{i\in down\_ taxonomies}{s}_i}\right)
$$

where *up*  \_  *taxonomies*, *down*  \_  *taxonomies* are the lists of taxonomies identified as higher and lower in Crohn’s disease, as listed in \[[^2]\].

For the performance evaluation, we used a leave-one-out approach. We iterated over all disease cohorts and for each iteration performed the analysis while leaving out a single validation disease cohort. The *up*  \_  *nonspecific*, *down*  \_  *nonspecific* ASV groups were identified as described above (see the “Identification of shared (“non-specific”) ASVs” section) but without the validation cohort (i.e., the non-specific ASVs were identified based on 58 disease cohorts). The dysbiosis index was then calculated for all samples of the validation cohort, and the *p* -value (for the null hypothesis of similar dysbiosis index distribution for cases and controls in the validation cohort) was tested using the non-parametric Mann-Whitney test with the single sided hypothesis (cases > controls).

### Data and code availability

Accession numbers for all studies used in the analysis are available in Additional file [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM1): supplementary table S1.

Commands and Scripts used for the generation of the per-study biom table and code are available in the sites Github and zenodo \[[^41], [^64]\].

## Availability of data and materials

Studies’ accession numbers are available in Additional file [1](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM1): table S1.

Scripts used for the generation of the per-study biom table, and code are available in the sites Github and zenodo \[[^41], [^64]\].

## References

## Acknowledgements

This work was supported by ARC and the Sheba Medical Center support of the Sheba Microbiome Center. YH is also supported by the Israel Science Foundation (908/15), the I-CORE program (41/11), Bill and Melinda Gates Foundation (OPP1144149), the Helmsley Charitable Trust, and the ERC (758313). We gratefully acknowledge Ornit Hall for reading through the manuscript and for her suggestions.

### Peer review information

Kevin Pang was the primary editor of this article and managed its editorial process and peer review in collaboration with the rest of the editorial team.

### Review history

The review history is available as Additional file [5](https://link.springer.com/article/10.1186/s13059-022-02637-7#MOESM5).

## Funding

ARC and the Sheba Medical Center support of the Sheba Microbiome Center. YH is also supported by the Israel Science Foundation (908/15), the I-CORE program (41/11), Bill and Melinda Gates Foundation (OPP1144149), and the Helmsley Charitable Trust, and the ERC (758313).

## Ethics declarations

### Ethics approval and consent to participate

Not applicable. All meta-analyses used publicly available de-identified datasets.

### Consent for publication

Not applicable

### Competing interests

The authors declare no competing interests.

## Additional information

### Publisher’s Note

Springer Nature remains neutral with regard to jurisdictional claims in published maps and institutional affiliations.

## Supplementary Information

### Additional file 1: Supplementary Table. (download DOCX )

Accession numbers for the studies used in the meta-analyses. **Figure S1.** The pipeline used for microbial characterization in our study overcomes cohort specific determinants and enables comparisons between disease cohorts. **Figure S2.** Non-specific microbial signal shared across diseases after rarefaction, and after using Lefse LDA. **Figure S3.** Prediction of the non-specific KEGG ontologies microbial signal shared across diseases. **Figure S4.** Disease classifier fails to predict control and disease samples when shuffling the samples before prediction. **Figure S5.** Dysbiosis index using UniDI and CD dysbiosis index. **Figure S6.** Dysbiosis index generated by the per-sample rank method (UniDI) showed more significant values between case/control samples.

### Additional file 2: Dataset S1. (download XLSX )

Non-specific ASVs signal (separate excel file) using initial NRMD, rarified NRMD (to 4K reads/sample), and LEFSE LDA.

### Additional file 3: Dataset S2. (download XLSX )

Per-ASV prediction of KEGG functions (PICRUSt2) significantly higher (or lower) in disease-associated non-specific bacteria.

### Additional file 4: Dataset S3. (download XLSX )

IBD-specific ASVs.

### Additional file 5. (download DOCX )

Review history.

## Rights and permissions

**Open Access** This article is licensed under a Creative Commons Attribution 4.0 International License, which permits use, sharing, adaptation, distribution and reproduction in any medium or format, as long as you give appropriate credit to the original author(s) and the source, provide a link to the Creative Commons licence, and indicate if changes were made. The images or other third party material in this article are included in the article's Creative Commons licence, unless indicated otherwise in a credit line to the material. If material is not included in the article's Creative Commons licence and your intended use is not permitted by statutory regulation or exceeds the permitted use, you will need to obtain permission directly from the copyright holder. To view a copy of this licence, visit [http://creativecommons.org/licenses/by/4.0/](http://creativecommons.org/licenses/by/4.0/). The Creative Commons Public Domain Dedication waiver ([http://creativecommons.org/publicdomain/zero/1.0/](http://creativecommons.org/publicdomain/zero/1.0/)) applies to the data made available in this article, unless otherwise stated in a credit line to the data.

[^1]: Braun T, et al. Individualized dynamics in the gut microbiota precede Crohn's disease flares. Am J Gastroenterol. 2019;114(7):1142–51.

[Article](https://doi.org/10.14309%2Fajg.0000000000000136) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=30741738) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Individualized%20dynamics%20in%20the%20gut%20microbiota%20precede%20Crohn%27s%20disease%20flares&journal=Am%20J%20Gastroenterol&doi=10.14309%2Fajg.0000000000000136&volume=114&issue=7&pages=1142-1151&publication_year=2019&author=Braun%2CT)

[^2]: Gevers D, et al. The treatment-naive microbiome in new-onset Crohn’s disease. Cell Host Microbe. 2014;15(3):382–92.

[Article](https://doi.org/10.1016%2Fj.chom.2014.02.005) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC2cXks1Omu7Y%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=24629344) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4059512) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20treatment-naive%20microbiome%20in%20new-onset%20Crohn%E2%80%99s%20disease&journal=Cell%20Host%20Microbe&doi=10.1016%2Fj.chom.2014.02.005&volume=15&issue=3&pages=382-392&publication_year=2014&author=Gevers%2CD)

[^3]: Haberman Y, et al. Pediatric Crohn disease patients exhibit specific ileal transcriptome and microbiome signature. J Clin Invest. 2014;124(8):3617–33.

[Article](https://doi.org/10.1172%2FJCI75436) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC2cXhtlGkt7rK) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=25003194) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4109533) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Pediatric%20Crohn%20disease%20patients%20exhibit%20specific%20ileal%20transcriptome%20and%20microbiome%20signature&journal=J%20Clin%20Invest&doi=10.1172%2FJCI75436&volume=124&issue=8&pages=3617-3633&publication_year=2014&author=Haberman%2CY)

[^4]: Pittayanon R, et al. Differences in gut microbiota in patients with vs without inflammatory bowel diseases: a systematic review. Gastroenterology. 2020;158(4):930–946 e1.

[Article](https://doi.org/10.1053%2Fj.gastro.2019.11.294) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31812509) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Differences%20in%20gut%20microbiota%20in%20patients%20with%20vs%20without%20inflammatory%20bowel%20diseases%3A%20a%20systematic%20review&journal=Gastroenterology&doi=10.1053%2Fj.gastro.2019.11.294&volume=158&issue=4&pages=930-946%20e1&publication_year=2020&author=Pittayanon%2CR)

[^5]: Duvallet C, et al. Meta-analysis of gut microbiome studies identifies disease-specific and shared responses. Nat Commun. 2017;8(1):1784.

[Article](https://doi.org/10.1038%2Fs41467-017-01973-8) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=29209090) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC5716994) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Meta-analysis%20of%20gut%20microbiome%20studies%20identifies%20disease-specific%20and%20shared%20responses&journal=Nat%20Commun&doi=10.1038%2Fs41467-017-01973-8&volume=8&issue=1&publication_year=2017&author=Duvallet%2CC)

[^6]: Mack I, et al. Weight gain in anorexia nervosa does not ameliorate the faecal microbiota, branched chain fatty acid profiles, and gastrointestinal complaints. Sci Rep. 2016;6:26752.

[Article](https://doi.org/10.1038%2Fsrep26752) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC28XptVSktL4%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=27229737) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4882621) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Weight%20gain%20in%20anorexia%20nervosa%20does%20not%20ameliorate%20the%20faecal%20microbiota%2C%20branched%20chain%20fatty%20acid%20profiles%2C%20and%20gastrointestinal%20complaints&journal=Sci%20Rep&doi=10.1038%2Fsrep26752&volume=6&publication_year=2016&author=Mack%2CI)

[^7]: Zurita MF, et al. Analysis of gut microbiome, nutrition and immune status in autism spectrum disorder: a case-control study in Ecuador. Gut Microbes. 2020;11(3):453–64.

[Article](https://doi.org/10.1080%2F19490976.2019.1662260) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31530087) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Analysis%20of%20gut%20microbiome%2C%20nutrition%20and%20immune%20status%20in%20autism%20spectrum%20disorder%3A%20a%20case-control%20study%20in%20Ecuador&journal=Gut%20Microbes&doi=10.1080%2F19490976.2019.1662260&volume=11&issue=3&pages=453-464&publication_year=2020&author=Zurita%2CMF)

[^8]: Vogt NM, et al. Gut microbiome alterations in Alzheimer’s disease. Sci Rep. 2017;7(1):13537.

[Article](https://doi.org/10.1038%2Fs41598-017-13601-y) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=29051531) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC5648830) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Gut%20microbiome%20alterations%20in%20Alzheimer%E2%80%99s%20disease&journal=Sci%20Rep&doi=10.1038%2Fs41598-017-13601-y&volume=7&issue=1&publication_year=2017&author=Vogt%2CNM)

[^9]: Evans SJ, et al. The gut microbiome composition associates with bipolar disorder and illness severity. J Psychiatr Res. 2017;87:23–9.

[Article](https://doi.org/10.1016%2Fj.jpsychires.2016.12.007) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=27988330) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20gut%20microbiome%20composition%20associates%20with%20bipolar%20disorder%20and%20illness%20severity&journal=J%20Psychiatr%20Res&doi=10.1016%2Fj.jpsychires.2016.12.007&volume=87&pages=23-29&publication_year=2017&author=Evans%2CSJ)

[^10]: Giloteaux L, et al. Reduced diversity and altered composition of the gut microbiome in individuals with myalgic encephalomyelitis/chronic fatigue syndrome. Microbiome. 2016;4(1):30.

[Article](https://link.springer.com/doi/10.1186/s40168-016-0171-4) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=27338587) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4918027) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Reduced%20diversity%20and%20altered%20composition%20of%20the%20gut%20microbiome%20in%20individuals%20with%20myalgic%20encephalomyelitis%2Fchronic%20fatigue%20syndrome&journal=Microbiome&doi=10.1186%2Fs40168-016-0171-4&volume=4&issue=1&publication_year=2016&author=Giloteaux%2CL)

[^11]: Cinek O, et al. The bacteriome at the onset of type 1 diabetes: a study from four geographically distant African and Asian countries. Diabetes Res Clin Pract. 2018;144:51–62.

[Article](https://doi.org/10.1016%2Fj.diabres.2018.08.010) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=30121305) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20bacteriome%20at%20the%20onset%20of%20type%201%20diabetes%3A%20a%20study%20from%20four%20geographically%20distant%20African%20and%20Asian%20countries&journal=Diabetes%20Res%20Clin%20Pract&doi=10.1016%2Fj.diabres.2018.08.010&volume=144&pages=51-62&publication_year=2018&author=Cinek%2CO)

[^12]: Kaplan RC, et al. Gut microbiome composition in the Hispanic Community Health Study/Study of Latinos is shaped by geographic relocation, environmental factors, and obesity. Genome Biol. 2019;20(1):219.

[Article](https://link.springer.com/doi/10.1186/s13059-019-1831-z) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31672155) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6824043) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Gut%20microbiome%20composition%20in%20the%20Hispanic%20Community%20Health%20Study%2FStudy%20of%20Latinos%20is%20shaped%20by%20geographic%20relocation%2C%20environmental%20factors%2C%20and%20obesity&journal=Genome%20Biol&doi=10.1186%2Fs13059-019-1831-z&volume=20&issue=1&publication_year=2019&author=Kaplan%2CRC)

[^13]: Li Q, et al. Implication of the gut microbiome composition of type 2 diabetic patients from northern China. Sci Rep. 2020;10(1):5450.

[Article](https://doi.org/10.1038%2Fs41598-020-62224-3) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=32214153) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC7096501) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Implication%20of%20the%20gut%20microbiome%20composition%20of%20type%202%20diabetic%20patients%20from%20northern%20China&journal=Sci%20Rep&doi=10.1038%2Fs41598-020-62224-3&volume=10&issue=1&publication_year=2020&author=Li%2CQ)

[^14]: Braun T, et al. Fecal microbial characterization of hospitalized patients with suspected infectious diarrhea shows significant dysbiosis. Sci Rep. 2017;7(1):1088.

[Article](https://doi.org/10.1038%2Fs41598-017-01217-1) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=28439072) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC5430810) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Fecal%20microbial%20characterization%20of%20hospitalized%20patients%20with%20suspected%20infectious%20diarrhea%20shows%20significant%20dysbiosis&journal=Sci%20Rep&doi=10.1038%2Fs41598-017-01217-1&volume=7&issue=1&publication_year=2017&author=Braun%2CT)

[^15]: Castano-Rodriguez N, et al. Gut microbiome analysis identifies potential etiological factors in acute gastroenteritis. Infect Immun. 2018;86(7):e00060–18.

[^16]: Liu Q, et al. Alteration in gut microbiota associated with hepatitis B and non-hepatitis virus related hepatocellular carcinoma. Gut Pathog. 2019;11:1.

[Article](https://link.springer.com/doi/10.1186/s13099-018-0281-6) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=30675188) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6337822) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Alteration%20in%20gut%20microbiota%20associated%20with%20hepatitis%20B%20and%20non-hepatitis%20virus%20related%20hepatocellular%20carcinoma&journal=Gut%20Pathog&doi=10.1186%2Fs13099-018-0281-6&volume=11&publication_year=2019&author=Liu%2CQ)

[^17]: Cook RR, et al. Alterations to the gastrointestinal microbiome associated with methamphetamine use among young men who have sex with men. Sci Rep. 2019;9(1):14840.

[Article](https://doi.org/10.1038%2Fs41598-019-51142-8) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31619731) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6795845) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Alterations%20to%20the%20gastrointestinal%20microbiome%20associated%20with%20methamphetamine%20use%20among%20young%20men%20who%20have%20sex%20with%20men&journal=Sci%20Rep&doi=10.1038%2Fs41598-019-51142-8&volume=9&issue=1&publication_year=2019&author=Cook%2CRR)

[^18]: Dillon SM, et al. An altered intestinal mucosal microbiome in HIV-1 infection is associated with mucosal and systemic immune activation and endotoxemia. Mucosal Immunol. 2014;7(4):983–94.

[Article](https://doi.org/10.1038%2Fmi.2013.116) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC2cXktFOqtg%3D%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=24399150) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4062575) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=An%20altered%20intestinal%20mucosal%20microbiome%20in%20HIV-1%20infection%20is%20associated%20with%20mucosal%20and%20systemic%20immune%20activation%20and%20endotoxemia&journal=Mucosal%20Immunol&doi=10.1038%2Fmi.2013.116&volume=7&issue=4&pages=983-994&publication_year=2014&author=Dillon%2CSM)

[^19]: Lozupone CA, et al. Alterations in the gut microbiota associated with HIV-1 infection. Cell Host Microbe. 2013;14(3):329–39.

[Article](https://doi.org/10.1016%2Fj.chom.2013.08.006) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC3sXhsVegtr3F) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=24034618) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Alterations%20in%20the%20gut%20microbiota%20associated%20with%20HIV-1%20infection&journal=Cell%20Host%20Microbe&doi=10.1016%2Fj.chom.2013.08.006&volume=14&issue=3&pages=329-339&publication_year=2013&author=Lozupone%2CCA)

[^20]: Vujkovic-Cvijin I, et al. HIV-associated gut dysbiosis is independent of sexual practice and correlates with noncommunicable diseases. Nat Commun. 2020;11(1):2448.

[Article](https://doi.org/10.1038%2Fs41467-020-16222-8) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BB3cXpslykurg%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=32415070) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC7228978) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=HIV-associated%20gut%20dysbiosis%20is%20independent%20of%20sexual%20practice%20and%20correlates%20with%20noncommunicable%20diseases&journal=Nat%20Commun&doi=10.1038%2Fs41467-020-16222-8&volume=11&issue=1&publication_year=2020&author=Vujkovic-Cvijin%2CI)

[^21]: Contijoch EJ, et al. Gut microbiota density influences host physiology and is shaped by host and microbial factors. Elife. 2019;8:e40553.

[^22]: Ijaz UZ, et al. The distinct features of microbial 'dysbiosis' of Crohn's disease do not occur to the same extent in their unaffected, genetically-linked kindred. PLoS One. 2017;12(2):e0172605.

[Article](https://doi.org/10.1371%2Fjournal.pone.0172605) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=28222161) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC5319678) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20distinct%20features%20of%20microbial%20%27dysbiosis%27%20of%20Crohn%27s%20disease%20do%20not%20occur%20to%20the%20same%20extent%20in%20their%20unaffected%2C%20genetically-linked%20kindred&journal=PLoS%20One&doi=10.1371%2Fjournal.pone.0172605&volume=12&issue=2&publication_year=2017&author=Ijaz%2CUZ)

[^23]: Shaw KA, et al. Dysbiosis, inflammation, and response to treatment: a longitudinal study of pediatric subjects with newly diagnosed inflammatory bowel disease. Genome Med. 2016;8(1):75.

[Article](https://link.springer.com/doi/10.1186/s13073-016-0331-y) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=27412252) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4944441) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Dysbiosis%2C%20inflammation%2C%20and%20response%20to%20treatment%3A%20a%20longitudinal%20study%20of%20pediatric%20subjects%20with%20newly%20diagnosed%20inflammatory%20bowel%20disease&journal=Genome%20Med&doi=10.1186%2Fs13073-016-0331-y&volume=8&issue=1&publication_year=2016&author=Shaw%2CKA)

[^24]: Zhou Y, et al. Gut microbiota offers universal biomarkers across ethnicity in inflammatory bowel disease diagnosis and infliximab response prediction. mSystems. 2018;3(1):e00188–17.

[^25]: Mar JS, et al. Disease severity and immune activity relate to distinct interkingdom gut microbiome states in ethnically distinct ulcerative colitis patients. mBio. 2016;7(4):e01072–16.

[^26]: Pozuelo M, et al. Reduction of butyrate- and methane-producing microorganisms in patients with irritable bowel syndrome. Sci Rep. 2015;5:12693.

[Article](https://doi.org/10.1038%2Fsrep12693) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC2MXhsVKiurbI) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=26239401) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4523847) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Reduction%20of%20butyrate-%20and%20methane-producing%20microorganisms%20in%20patients%20with%20irritable%20bowel%20syndrome&journal=Sci%20Rep&doi=10.1038%2Fsrep12693&volume=5&publication_year=2015&author=Pozuelo%2CM)

[^27]: Luo XM, et al. Gut microbiota in human systemic lupus erythematosus and a mouse model of lupus. Appl Environ Microbiol. 2018;84(4):e02288–17.

[^28]: de la Cuesta-Zuluaga J, et al. Gut microbiota is associated with obesity and cardiometabolic disease in a population in the midst of Westernization. Sci Rep. 2018;8(1):11356.

[Article](https://doi.org/10.1038%2Fs41598-018-29687-x) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=30054529) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6063892) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Gut%20microbiota%20is%20associated%20with%20obesity%20and%20cardiometabolic%20disease%20in%20a%20population%20in%20the%20midst%20of%20Westernization&journal=Sci%20Rep&doi=10.1038%2Fs41598-018-29687-x&volume=8&issue=1&publication_year=2018&author=Cuesta-Zuluaga%2CJ)

[^29]: Vangay P, et al. US immigration westernizes the human gut microbiome. Cell. 2018;175(4):962–972 e10.

[Article](https://doi.org/10.1016%2Fj.cell.2018.10.029) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC1cXitVyhurjO) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=30388453) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6498444) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=US%20immigration%20westernizes%20the%20human%20gut%20microbiome&journal=Cell&doi=10.1016%2Fj.cell.2018.10.029&volume=175&issue=4&pages=962-972%20e10&publication_year=2018&author=Vangay%2CP)

[^30]: Zhu Y, et al. Gut microbiota dysbiosis worsens the severity of acute pancreatitis in patients and mice. J Gastroenterol. 2019;54(4):347–58.

[Article](https://link.springer.com/doi/10.1007/s00535-018-1529-0) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC1cXisVaku7bI) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=30519748) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Gut%20microbiota%20dysbiosis%20worsens%20the%20severity%20of%20acute%20pancreatitis%20in%20patients%20and%20mice&journal=J%20Gastroenterol&doi=10.1007%2Fs00535-018-1529-0&volume=54&issue=4&pages=347-358&publication_year=2019&author=Zhu%2CY)

[^31]: Heintz-Buschart A, et al. The nasal and gut microbiome in Parkinson’s disease and idiopathic rapid eye movement sleep behavior disorder. Mov Disord. 2018;33(1):88–98.

[Article](https://doi.org/10.1002%2Fmds.27105) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC1cXhtlKnu7k%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=28843021) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20nasal%20and%20gut%20microbiome%20in%20Parkinson%E2%80%99s%20disease%20and%20idiopathic%20rapid%20eye%20movement%20sleep%20behavior%20disorder&journal=Mov%20Disord&doi=10.1002%2Fmds.27105&volume=33&issue=1&pages=88-98&publication_year=2018&author=Heintz-Buschart%2CA)

[^32]: Hill-Burns EM, et al. Parkinson’s disease and Parkinson’s disease medications have distinct signatures of the gut microbiome. Mov Disord. 2017;32(5):739–49.

[Article](https://doi.org/10.1002%2Fmds.26942) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC2sXnvFChsb4%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=28195358) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC5469442) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Parkinson%E2%80%99s%20disease%20and%20Parkinson%E2%80%99s%20disease%20medications%20have%20distinct%20signatures%20of%20the%20gut%20microbiome&journal=Mov%20Disord&doi=10.1002%2Fmds.26942&volume=32&issue=5&pages=739-749&publication_year=2017&author=Hill-Burns%2CEM)

[^33]: Wallen ZD, et al. Characterizing dysbiosis of gut microbiome in PD: evidence for overabundance of opportunistic pathogens. NPJ Parkinsons Dis. 2020;6:11.

[Article](https://doi.org/10.1038%2Fs41531-020-0112-6) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BB3cXht1CmsbjL) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=32566740) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC7293233) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Characterizing%20dysbiosis%20of%20gut%20microbiome%20in%20PD%3A%20evidence%20for%20overabundance%20of%20opportunistic%20pathogens&journal=NPJ%20Parkinsons%20Dis&doi=10.1038%2Fs41531-020-0112-6&volume=6&publication_year=2020&author=Wallen%2CZD)

[^34]: Nguyen TT, et al. Differences in gut microbiome composition between persons with chronic schizophrenia and healthy comparison subjects. Schizophr Res. 2019;204:23–9.

[Article](https://doi.org/10.1016%2Fj.schres.2018.09.014) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=30268819) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Differences%20in%20gut%20microbiome%20composition%20between%20persons%20with%20chronic%20schizophrenia%20and%20healthy%20comparison%20subjects&journal=Schizophr%20Res&doi=10.1016%2Fj.schres.2018.09.014&volume=204&pages=23-29&publication_year=2019&author=Nguyen%2CTT)

[^35]: Xu R, et al. Altered gut microbiota and mucosal immunity in patients with schizophrenia. Brain Behav Immun. 2020;85:120–7.

[Article](https://doi.org/10.1016%2Fj.bbi.2019.06.039) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC1MXhtlahsL3E) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31255682) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Altered%20gut%20microbiota%20and%20mucosal%20immunity%20in%20patients%20with%20schizophrenia&journal=Brain%20Behav%20Immun&doi=10.1016%2Fj.bbi.2019.06.039&volume=85&pages=120-127&publication_year=2020&author=Xu%2CR)

[^36]: Sinha R, et al. Assessment of variation in microbial community amplicon sequencing by the Microbiome Quality Control (MBQC) project consortium. Nat Biotechnol. 2017;35(11):1077–86.

[Article](https://doi.org/10.1038%2Fnbt.3981) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC2sXhsFylurvE) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=28967885) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC5839636) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Assessment%20of%20variation%20in%20microbial%20community%20amplicon%20sequencing%20by%20the%20Microbiome%20Quality%20Control%20%28MBQC%29%20project%20consortium&journal=Nat%20Biotechnol&doi=10.1038%2Fnbt.3981&volume=35&issue=11&pages=1077-1086&publication_year=2017&author=Sinha%2CR)

[^37]: Jiang L, et al. Discrete false-discovery rate improves identification of differentially abundant microbes. mSystems. 2017;2(6):e00092–17.

[^38]: Segata N, et al. Metagenomic biomarker discovery and explanation. Genome Biol. 2011;12(6):R60.

[Article](https://link.springer.com/doi/10.1186/gb-2011-12-6-r60) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=21702898) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3218848) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Metagenomic%20biomarker%20discovery%20and%20explanation&journal=Genome%20Biol&doi=10.1186%2Fgb-2011-12-6-r60&volume=12&issue=6&publication_year=2011&author=Segata%2CN)

[^39]: Douglas GM, et al. PICRUSt2 for prediction of metagenome functions. Nat Biotechnol. 2020;38(6):685–8.

[Article](https://doi.org/10.1038%2Fs41587-020-0548-6) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BB3cXhtVGmtb3I) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=32483366) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC7365738) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=PICRUSt2%20for%20prediction%20of%20metagenome%20functions&journal=Nat%20Biotechnol&doi=10.1038%2Fs41587-020-0548-6&volume=38&issue=6&pages=685-688&publication_year=2020&author=Douglas%2CGM)

[^40]: Antunes LCM, et al. Quorum sensing in bacterial virulence. Microbiology (Reading). 2010;156(Pt 8):2271–82.

[Article](https://doi.org/10.1099%2Fmic.0.038794-0) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC3cXhtFSltLrE) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Quorum%20sensing%20in%20bacterial%20virulence&journal=Microbiology%20%28Reading%29&doi=10.1099%2Fmic.0.038794-0&volume=156&issue=Pt%208&pages=2271-2282&publication_year=2010&author=Antunes%2CLCM)

[^41]: Haya A-E, Yael H, Tzipi B, Rotem H, Lee D, Ohad G-M, et al. Meta-analysis defines predominant shared microbial responses in various diseases and a specific inflammatory bowel disease signal. Zenodo. 2022. [https://doi.org/10.5281/zenodo.6054449](https://doi.org/10.5281/zenodo.6054449)

[^42]: Gomez A, et al. Host genetic control of the oral microbiome in health and disease. Cell Host Microbe. 2017;22(3):269–278 e3.

[Article](https://doi.org/10.1016%2Fj.chom.2017.08.013) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC2sXhsFSktLfI) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=28910633) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC5733791) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Host%20genetic%20control%20of%20the%20oral%20microbiome%20in%20health%20and%20disease&journal=Cell%20Host%20Microbe&doi=10.1016%2Fj.chom.2017.08.013&volume=22&issue=3&pages=269-278%20e3&publication_year=2017&author=Gomez%2CA)

[^43]: Topcuoglu BD, et al. A framework for effective application of machine learning to microbiome-based classification problems. mBio. 2020;11(3):e00434–20.

[^44]: Kobayashi R, et al. Oral bacteria affect the gut microbiome and intestinal immunity. Pathog Dis. 2020;78(3):ftaa024.

[^45]: Wirbel J, et al. Microbiome meta-analysis and cross-disease comparison enabled by the SIAMCAT machine learning toolbox. Genome Biol. 2021;22(1):93.

[Article](https://link.springer.com/doi/10.1186/s13059-021-02306-1) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=33785070) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC8008609) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Microbiome%20meta-analysis%20and%20cross-disease%20comparison%20enabled%20by%20the%20SIAMCAT%20machine%20learning%20toolbox&journal=Genome%20Biol&doi=10.1186%2Fs13059-021-02306-1&volume=22&issue=1&publication_year=2021&author=Wirbel%2CJ)

[^46]: Armour CR, et al. A metagenomic meta-analysis reveals functional signatures of health and disease in the human gut microbiome. mSystems. 2019;4(4):e00332–18.

[^47]: Carmody LA, et al. Changes in cystic fibrosis airway microbiota at pulmonary exacerbation. Ann Am Thorac Soc. 2013;10(3):179–87.

[Article](https://doi.org/10.1513%2FAnnalsATS.201211-107OC) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=23802813) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3960905) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Changes%20in%20cystic%20fibrosis%20airway%20microbiota%20at%20pulmonary%20exacerbation&journal=Ann%20Am%20Thorac%20Soc&doi=10.1513%2FAnnalsATS.201211-107OC&volume=10&issue=3&pages=179-187&publication_year=2013&author=Carmody%2CLA)

[^48]: Pascal V, et al. A microbial signature for Crohn's disease. Gut. 2017;66(5):813–22.

[Article](https://doi.org/10.1136%2Fgutjnl-2016-313235) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC1cXhtFKms73E) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=28179361) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=A%20microbial%20signature%20for%20Crohn%27s%20disease&journal=Gut&doi=10.1136%2Fgutjnl-2016-313235&volume=66&issue=5&pages=813-822&publication_year=2017&author=Pascal%2CV)

[^49]: Mashima I, Nakazawa F. The interaction between Streptococcus spp. and Veillonella tobetsuensis in the early stages of oral biofilm formation. J Bacteriol. 2015;197(3):2104–11.

[Article](https://doi.org/10.1128%2FJB.02512-14) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC2MXhtVCrsrrI) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=25917902) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4455269) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20interaction%20between%20Streptococcus%20spp.%20and%20Veillonella%20tobetsuensis%20in%20the%20early%20stages%20of%20oral%20biofilm%20formation&journal=J%20Bacteriol&doi=10.1128%2FJB.02512-14&volume=197&issue=3&pages=2104-2111&publication_year=2015&author=Mashima%2CI&author=Nakazawa%2CF)

[^50]: van den Bogert B, et al. Immunomodulatory properties of Streptococcus and Veillonella isolates from the human small intestine microbiota. PLoS One. 2014;9(12):e114277.

[Article](https://doi.org/10.1371%2Fjournal.pone.0114277) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=25479553) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4257559) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Immunomodulatory%20properties%20of%20Streptococcus%20and%20Veillonella%20isolates%20from%20the%20human%20small%20intestine%20microbiota&journal=PLoS%20One&doi=10.1371%2Fjournal.pone.0114277&volume=9&issue=12&publication_year=2014&author=Bogert%2CB)

[^51]: Dubinsky V, et al. Predominantly antibiotic-resistant intestinal microbiome persists in patients with pouchitis who respond to antibiotic therapy. Gastroenterology. 2020;158(3):610–624 e13.

[Article](https://doi.org/10.1053%2Fj.gastro.2019.10.001) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BB3cXlsFeqtbo%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31605691) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Predominantly%20antibiotic-resistant%20intestinal%20microbiome%20persists%20in%20patients%20with%20pouchitis%20who%20respond%20to%20antibiotic%20therapy&journal=Gastroenterology&doi=10.1053%2Fj.gastro.2019.10.001&volume=158&issue=3&pages=610-624%20e13&publication_year=2020&author=Dubinsky%2CV)

[^52]: Lloyd-Price J, et al. Multi-omics of the gut microbial ecosystem in inflammatory bowel diseases. Nature. 2019;569(7758):655–62.

[Article](https://doi.org/10.1038%2Fs41586-019-1237-9) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC1MXhtVOgtL3O) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31142855) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6650278) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Multi-omics%20of%20the%20gut%20microbial%20ecosystem%20in%20inflammatory%20bowel%20diseases&journal=Nature&doi=10.1038%2Fs41586-019-1237-9&volume=569&issue=7758&pages=655-662&publication_year=2019&author=Lloyd-Price%2CJ)

[^53]: Sartor RB. Microbial influences in inflammatory bowel diseases. Gastroenterology. 2008;134(2):577–94.

[Article](https://doi.org/10.1053%2Fj.gastro.2007.11.059) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BD1cXivFOjs7o%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=18242222) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Microbial%20influences%20in%20inflammatory%20bowel%20diseases&journal=Gastroenterology&doi=10.1053%2Fj.gastro.2007.11.059&volume=134&issue=2&pages=577-594&publication_year=2008&author=Sartor%2CRB)

[^54]: Gupta VK, et al. A predictive index for health status using species-level gut microbiome profiling. Nat Commun. 2020;11(1):4635.

[Article](https://doi.org/10.1038%2Fs41467-020-18476-8) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BB3cXhvVyns7zE) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=32934239) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC7492273) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=A%20predictive%20index%20for%20health%20status%20using%20species-level%20gut%20microbiome%20profiling&journal=Nat%20Commun&doi=10.1038%2Fs41467-020-18476-8&volume=11&issue=1&publication_year=2020&author=Gupta%2CVK)

[^55]: Magro DO, et al. Remission in Crohn’s disease is accompanied by alterations in the gut microbiota and mucins production. Sci Rep. 2019;9(1):13263.

[Article](https://doi.org/10.1038%2Fs41598-019-49893-5) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31520001) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6744406) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Remission%20in%20Crohn%E2%80%99s%20disease%20is%20accompanied%20by%20alterations%20in%20the%20gut%20microbiota%20and%20mucins%20production&journal=Sci%20Rep&doi=10.1038%2Fs41598-019-49893-5&volume=9&issue=1&publication_year=2019&author=Magro%2CDO)

[^56]: Amir A, et al. Gut microbiome development in early childhood is affected by day care attendance. NPJ Biofilms Microbiomes. 2022;8(1):2.

[Article](https://doi.org/10.1038%2Fs41522-021-00265-w) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=35017536) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC8752763) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Gut%20microbiome%20development%20in%20early%20childhood%20is%20affected%20by%20day%20care%20attendance&journal=NPJ%20Biofilms%20Microbiomes&doi=10.1038%2Fs41522-021-00265-w&volume=8&issue=1&publication_year=2022&author=Amir%2CA)

[^57]: Amir A, et al. Deblur rapidly resolves single-nucleotide community sequence patterns. mSystems. 2017;2(2):e00191–16.

[^58]: Bolyen E, et al. Reproducible, interactive, scalable and extensible microbiome data science using QIIME 2. Nat Biotechnol. 2019;37(8):852–7.

[Article](https://doi.org/10.1038%2Fs41587-019-0209-9) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC1MXhsVeksr%2FO) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31341288) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC7015180) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Reproducible%2C%20interactive%2C%20scalable%20and%20extensible%20microbiome%20data%20science%20using%20QIIME%202&journal=Nat%20Biotechnol&doi=10.1038%2Fs41587-019-0209-9&volume=37&issue=8&pages=852-857&publication_year=2019&author=Bolyen%2CE)

[^59]: Amir A, et al. Correcting for microbial blooms in fecal samples during room-temperature shipping. mSystems. 2017;2(2):e00199–16.

[^60]: Bokulich NA, et al. Optimizing taxonomic classification of marker-gene amplicon sequences with QIIME 2's q2-feature-classifier plugin. Microbiome. 2018;6(1):90.

[Article](https://link.springer.com/doi/10.1186/s40168-018-0470-z) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=29773078) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC5956843) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Optimizing%20taxonomic%20classification%20of%20marker-gene%20amplicon%20sequences%20with%20QIIME%202%27s%20q2-feature-classifier%20plugin&journal=Microbiome&doi=10.1186%2Fs40168-018-0470-z&volume=6&issue=1&publication_year=2018&author=Bokulich%2CNA)

[^61]: Oksanen JEA. vegan: Community Ecology Package. R package version 2.5-3; 2018.

[Google Scholar](http://scholar.google.com/scholar_lookup?&title=vegan%3A%20Community%20Ecology%20Package.%20R%20package%20version%202.5-3&publication_year=2018&author=Oksanen%2CJEA)

[^62]: Xu ZZ, et al. Calour: an interactive, microbe-centric analysis tool. mSystems. 2019;4(1):e00269–18.

[^63]: Halsey LG, et al. The fickle P value generates irreproducible results. Nat Methods. 2015;12(3):179–85.

[Article](https://doi.org/10.1038%2Fnmeth.3288) [CAS](https://link.springer.com/articles/cas-redirect/1:CAS:528:DC%2BC2MXjsVagu7o%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=25719825) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20fickle%20P%20value%20generates%20irreproducible%20results&journal=Nat%20Methods&doi=10.1038%2Fnmeth.3288&volume=12&issue=3&pages=179-185&publication_year=2015&author=Halsey%2CLG)

[^64]: Haya A-E, Yael H, Tzipi B, Rotem H, Lee D, Ohad G-M, et al. Meta-analysis defines predominant shared microbial responses in various diseases and a specific inflammatory bowel disease signal. Github.2022. [https://github.com/amnona/paper-metaanalysis.git](https://github.com/amnona/paper-metaanalysis.git)