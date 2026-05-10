---
title: "Multi-omics data integration identifies novel biomarkers and patient subgroups in inflammatory bowel disease"
source: "https://academic.oup.com/ecco-jcc/article/19/1/jjae197/7942687"
author:
  - "[[António José Preto]]"
  - "[[Shaurya Chanana]]"
  - "[[Daniel Ence]]"
  - "[[Matthew D Healy]]"
  - "[[Daniel Domingo-Fernández]]"
  - "[[Kiana A West]]"
published: 2025-01-04
created: 2026-05-02
description: "AbstractBackground. Inflammatory bowel disease (IBD), comprising Crohn’s disease (CD) and ulcerative colitis (UC), is a complex condition with diverse mani"
tags:
  - "clippings"
---
## Abstract

Background

Inflammatory bowel disease (IBD), comprising Crohn’s disease (CD) and ulcerative colitis (UC), is a complex condition with diverse manifestations; recent advances in multi-omics technologies are helping researchers unravel its molecular characteristics to develop targeted treatments.

Objectives

In this work, we explored one of the largest multi-omics cohorts in IBD, the Study of a Prospective Adult Research Cohort (SPARC IBD), with the goal of identifying predictive biomarkers for CD and UC and elucidating patient subtypes.

Design

We analyzed genomics, transcriptomics (gut biopsy samples), and proteomics (blood plasma) from hundreds of patients from SPARC IBD. We trained a machine learning model that classifies UC versus CD samples. In parallel, we integrated multi-omics data to unveil patient subgroups in each of the 2 indications independently and analyzed the molecular phenotypes of these patient subpopulations.

Results

The high performance of the model showed that multi-omics signatures are able to discriminate between the 2 indications. The most predictive features of the model, both known and novel omics signatures for IBD, can potentially be used as diagnostic biomarkers. Patient subgroup analysis in each indication uncovered omics features associated with disease severity in UC patients and with tissue inflammation in CD patients. This culminates with the observation of 2 CD subpopulations characterized by distinct inflammation profiles.

Conclusions

Our work unveiled potential biomarkers to discriminate between CD and UC and to stratify each population into well-defined subgroups, offering promising avenues for the application of precision medicine strategies.

Graphical Abstract

[Open in new tab](https://academic.oup.com/view-large/figure/505279294/jjae197_fig6.jpg?itm_medium=graphical+abstract+image&itm_content=open+image&itm_source=http://academic.oup.com/ecco-jcc/article/19/1/jjae197/7942687&itm_campaign=graphical+abstract) [Download slide](https://academic.oup.com/DownloadFile/DownloadImage.aspx?image=https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_fig6.jpeg?Expires=1779271534&Signature=sW5eQuzvuloWA~0zmGTTHYBz25PZvsOh4uvzS3~~Jl9VNowdiPlwZpDHooRFVu2O-1WqToC1crp17VVstKVp9pssL8~zlb8eWXoiSArh6wo3qrIzzaJ9Vz7pXF8tro90P9JHLnzPDngWC1jDFyAPBDmUUhdwFKLxSVYBtDBgOujwT2scVgUJFP-jXWvdm40dzyjooEuWBegjUghFLrbwHhcZgD~YBeLT0Hg-UwrAfICOHRm6f6v1QgRakrzcVST1YShdm~VrizX5jZa6KsjbSJX5yAU0EpMcAYvIaYfL2Grs7O7I9l7WSmEwspld-l8nSxSpMMCbs082LxYp~-WAXg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA&sec=505279294&ar=7942687&xsltPath=~/UI/app/XSLT&imagename=&siteId=5398&itm_medium=graphical+abstract+image&itm_content=download+button&itm_source=http://academic.oup.com/ecco-jcc/article/19/1/jjae197/7942687&itm_campaign=graphical+abstract)

## 1\. Introduction

Inflammatory bowel disease (IBD) encompasses Crohn’s disease (CD) and ulcerative colitis (UC), both of which are chronic and complex conditions that impact the gastrointestinal tract. Characterized by its heterogeneity, IBD presents a spectrum of disease manifestations, including variability in disease location within the gastrointestinal tract, disease behaviors, and levels of disease activity among patients.<sup>1</sup> Despite significant research efforts aimed at unraveling the disease’s complexity—ranging from identifying genetic variants and environmental factors to analyzing the gut microbiome—the pathophysiological mechanisms defining the distinct clinical subtypes of IBD remain partially understood. The challenge lies in pinpointing the specific molecular pathways that contribute to this heterogeneity and developing targeted treatment approaches.

The emergence of multi-omics technologies has opened new pathways for understanding the intricate biological networks at play in IBD.<sup>2–4</sup> By generating and analyzing genomics, transcriptomics, proteomics, and metabolomics data, researchers can now better understand the molecular characteristics of IBD.<sup>5</sup> Several projects have been initiated to amass patient-level omics data, demonstrating the commitment to this comprehensive approach.<sup>6</sup> Notable examples include the 1000IBD project, which has collected genomics, gut microbiome taxonomic profiles, and fecal metagenomics from over 1000 patients,<sup>7</sup> and the IBD database, featuring a wide range of omics data from more than 100 patients.<sup>3</sup> Additionally, the International Inflammatory Bowel Disease Genetics Consortium focuses on genetic data from thousands of patients globally. Yet many of these initiatives have primarily concentrated on metagenomics and genomics, often overlooking proteomics and transcriptomics from blood and biopsies. The recent Study of a Prospective Adult Research Cohort (SPARC) IBD cohort aims to bridge this gap by enrolling over 3000 CD and UC patients and incorporating a diverse array of omics data, thus paving the way for groundbreaking insights into the disease.<sup>8</sup>

Leveraging such cohorts, research efforts have focused on identifying biomarker signatures for IBD. For instance, Mo and colleagues <sup>9</sup> used transcriptomics data from 357 UC patients to cluster them into 3 subpopulations correlated with clinical responses. Similarly, Janker and colleagues <sup>10</sup> examined proteomics and metabolomics in blood plasma and colon tissue from UC patients, those in remission, and controls, revealing upregulation of inflammatory pathways in active UC, which normalize upon remission. This analysis utilized mixOmics and Gaussian modeling, though the study’s impact was limited by its small sample size. In a broader approach,<sup>11</sup> utilized the SPARC dataset to examine the correlation between noninvasive biomarkers c-reactive protein (CRP) and fecal calprotectin (FCP) and patient-reported outcomes, discovering that while there is a correlation, it varies by disease location and type.

In this work, we leveraged the largest multi-omics IBD dataset available in pursuit of novel, clinically relevant biomarkers for diagnostics and patient stratification. We used machine learning (ML) to empirically determine multiple omics features that distinguish UC from CD patients, resulting in potential biomarkers that may aid the diagnosis of patients with indeterminate colitis. In parallel, we integrated multiple omics layers to identify and characterize patient subpopulations based on clinical phenotypes such as disease severity and intestinal inflammation.

## 2\. Methods

The results published here are based on data obtained from the IBD Plexus program of the Crohn’s & Colitis Foundation. Figure 1 outlines the methodology of this work and the structure of the methods section. The first subsection describes the SPARC IBD cohort and the 3 omics modalities used (Figure 1 left). The following 2 sections outline the preparation and processing of multi-omics data (Figure 1 center). Finally, in the last 2 subsections, we describe the supervised ML classifier and the unsupervised method, Multi-Omics Factor Analysis (MOFA) used in this work (Figure 1 right).

![Graphical abstract.](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/m_jjae197_fig1.jpeg?Expires=1779271534&Signature=rlozJ4wLQbOz0zkJa3g3kABUJ467RLWCzMJRjczyzZ8nmegfVbjyGCYjLjuOGy3wZ0S~lc7c-k8PXuH-Tdc1Z13pQUpL0FjwxleeFs~jG-zMpi7szOcM~XYa1av-7o6N2YVj0Y6CS8Cp7r4-9npRM00y51~EiHmrspwKbPm7dDpFDnGHqbGQixtquj6~ftfPgq-EwH11OF3pfn~8kuOkwyh6nj9n4c5s32bNDsscGrLfQiIX1G0ucwwP39VoKdLJkFxABWRWbkczbDl5zZ0z98HKyxoA3s8KdnAJSGnooUZKzkH3dwyOSTyTjBh4oSv1VmEe2EPvlvm3AYoDGbg5FQ__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)

Figure 1.

Outline of the methodology. The starting point of our work is 3 types of omics data (proteomics, genomics, and transcriptomics) generated from samples from inflammatory bowel disease (IBD) patients (ie, Crohn’s disease \[CD\] and ulcerative colitis \[UC\]). We processed these 3 omics modalities to generate a multi-omics dataset. In 1 venue, we combined the omics data and trained an ML classifier that can accurately differentiate between samples derived from UC and CD patients. Parallely, we explored the characteristics of different subpopulations in each indication (CD and UC) using Multi‐Omics Factor Analysis (MOFA). This figure was created by using BioRender.com.

[Open in new tab](https://academic.oup.com/view-large/figure/505279303/jjae197_fig1.jpg) [Download slide](https://academic.oup.com/DownloadFile/DownloadImage.aspx?image=https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_fig1.jpeg?Expires=1779271534&Signature=sl9JDFIDabIFZ~E4-S~Gkfhjrut~qw7NcsvbJ2jpoarzuGxC0XmD8Qsxe-cZ-~R5kdyf-jmbvAOe7izt3xfrx6Kvt6egFopi~YZjdhbu-WLC6fl6bkLm042yrfRlcRPqNQ0247pAPqg0ODis7IN8xDBCx7Io~1sEerUf0T6z2XjyID1FjfsWM~TFFiOHaJ165YaRoSY~c-WhMGm-m6itgduHE29VQVGh8fJawcYpXXNkB6urHIp2Pc6o078oJUGTiNgDXXOr3QmSjB0qkxYRredaOCd-JyQ2qo0Ptn42YtSDOG1dCPYojmMweVgTSVtaryvT1Fl7kc2vB7tgpVzPrg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA&sec=505279303&ar=7942687&xsltPath=~/UI/app/XSLT&imagename=&siteId=5398)

### 2.1. SPARC IBD cohort

The starting point for this research is the SPARC IBD, a component of the Crohn’s & Colitis Foundation’s IBD Plexus research platform. The SPARC IBD cohort, as of April 2024, contained multiple data modalities across different timepoints for several thousands of patients with IBD. For the purpose of this work, we subset the full cohort to samples of patients characterized by 3 omics modalities: genomics, transcriptomics, and proteomics ([Figure S1](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)). Table 1 summarizes the different batches across these 3 omics modalities for the 603 patients with all 3 omics modalities available in the same valid time intervals (1 week); for these patients, there are 1184 intervals. We refer to [Text S1](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA) and Raffals et al.<sup>8</sup> for details about the raw genomics, proteomics, and transcriptomics data, as well as how the raw data were processed internally to generate the SPARC IBD cohort. Similarly, [Table S2](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA) describes the patient demographics.

Table 1.

[Open in new tab](https://academic.oup.com/view-large/505279306)

Numbers of samples stratified by batch and omics modality from the 603 patients and 1184 patient-intervals with all 3 omics modalities available.

| SPARC IBD cohort batch | Modality | Number of samples | Number of patients |
| --- | --- | --- | --- |
| sparc-genotyping | Genomics | 603 | 603 |
| sparc-genewiz-2021 | Transcriptomics | 322 | 170 |
| sparc-cd-genewiz | Transcriptomics | 230 | 131 |
| sparc-genewiz | Transcriptomics | 224 | 126 |
| sparc-genewiz-2022 | Transcriptomics | 408 | 176 |
| sparc-olink | Proteomics | 706 | 603 |

### 2.2. Data processing

Starting from the preprocessed data provided by the SPARC IBD cohort ([Text S1](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)), we dropped transcripts without a gene name. Using PyDESeq2,<sup>12</sup> we normalized each of the batches and multiplied by the size factors (ie, related to the number of reads in the library), thus making the expression values independent from the number of reads. We also removed features with zero variance (ie, the same value across all samples).

Next, we deployed multiple standard approaches to minimize the batch effect observed in the transcriptomics data, such as pyComBat <sup>13</sup> and linear modeling with limma.<sup>14</sup> However, this step alone was unable to successfully minimize the batch effect; batch remained the main source of variance for numerous transcriptomics features. To mitigate this technical variation, we added an additional step to the batch effect correction approach. For each of the features, we calculated the average of the variance for each of the batches (henceforth, intra-batch variance) and dropped the features where the intra-batch variance was lower than 0.05. We performed batch correction on the remaining features using pyComBat. We processed genomics data using VCFtools <sup>15</sup> by reducing the raw data to biallelic sites with a minor allele frequency of at least 0.05. We annotated the data using PyEnsembl, with the Ensembl 110 release of the human genome (GRCh38.p14) of the human database.<sup>16</sup> Proteomics data were used as provided without features tagged as low quality (ie, “QC warning”) and QC samples.

Lastly, we matched all 3 omics for each patient by collection date with a threshold of 7 days (details in [Text S2](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)). After collapsing the metadata, we arrive at a total of 1431 patients with transcriptomics data, 1563 patients with proteomics data, and 1641 patients with genomics array information. Hereafter, we will refer to the genomics information solely as the genomics array information. In the intersection of the 3 omics types, we have 603 patients with 1184 interval-unique patients ([Figure S2](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)). For the following analyses, we exclusively considered samples from these patients with all 3 omics.

Regarding the features, for each omics type, and after removing the features with null variance, we arrived at 166 916 for genomics, 19 442 for transcriptomics, and 2940 for proteomics.

### 2.3. Building an ML model to classify UC versus CD

We trained an XGBoost classifier (XGBoost Python v2.0.3) <sup>17</sup> to predict whether the omics data originated from UC or CD patients (CD: 779 intervals from 293 patients; UC: 393 intervals from 207 patients) ([Figure S3](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)). Regarding the transcriptomics data, the model was trained solely on the colon samples, as it was the only tissue present in both the UC and CD patients (CD: 391 intervals from 344 patients; UC: 225 intervals from 193 patients). We chose this model as it is considered to be state-of-the-art in generic tabular data as well as on similar large biomedical cohorts.<sup>18</sup> Furthermore, while neural network architectures could have been used, we preferred XGBoost due to its inherent interpretability and its aforementioned consistent high performance in similar data.

To evaluate the performance of the model, we first performed an 80/20 split on the unique patient identifiers, generating independent train and test sets. We normalized the training and test data by subtracting the mean and scaling from the variance of the training data. We trained the model using a nested 5-fold stratified cross-validation on the training set. Specifically, we trained a hyperparameter-optimized model on each of the 5 train-validation splits. Parameters for each model were optimized using 5-fold cross-validation exclusively within the training set of each fold to avoid overfitting. Splits were stratified to equalize the relative proportions of UC and CD patients. The hyperparameters used, and their ranges are shown in [Table S1](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA). We evaluate the 5 models on the test and validation sets in order to deliver the performance results by metric and its respective standard deviation across the models. The performance evaluation metrics used in this categorical prediction setting are accuracy, F1-score, area under the curve of the receiver-operating characteristic curve (AUC-ROC), precision, and recall. Finally, we look at the most predictive features of the model based on gain, which measures the increase in performance brought by a feature in the branches it acts upon.

### 2.4. Multi-omics-driven clustering

In order to perform unsupervised patient stratification, we leveraged MOFA.<sup>19</sup> Our goal when using this technique was to simultaneously perform the integration of multiple omics data sources and types as well as identify sets of descriptors that explain biological and physiological functions. Ultimately, we aimed to identify phenotypic-driven clusters of patient samples that are likely more responsive to different therapies.

CD and UC are heterogeneous conditions with multiple subtypes.<sup>20</sup> To account for this, we separately ran MOFA analyses for each diagnosis (CD and UC). Considering the specificity of transcriptomics patterns in different tissues,<sup>21</sup> which we observed later on in our analyses (Section ), we focused solely on the colon samples for UC and modeled colon samples separately from small intestine samples for CD. We independently standardized the omics’ data features by removing the mean and scaling to unit variance prior to modeling. We refer to [Text S3](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA) for more details about MOFA and the parameters used and [Figure S4](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA) for an overview of the MOFA.

We identify the factors of interest by their relationship to either macroscopic appearance (intestinal inflammation based on the biopsy sampled) or disease severity. The factors are a result of the weighted contributions of features that are likely to be involved in similar biological functions.<sup>19</sup> From these factors, and for each omics type, we retrieve the omics signatures with the highest absolute weights for that factor. On this selection of features, we conducted pathway analysis using GSEApy <sup>22</sup> with the gene sets from GO Biological Process (2023), considering enriched pathways as the ones with an adjusted *P* -value less than.01. Pathways were ranked according to the combined score returned by EnrichR.<sup>23</sup>

## 3\. Results

### 3.1. Correcting for batch effect unlocks the power of multi-omics data

We found that the transcriptomics data exhibited a strong batch effect that was the predominant source of variation and hindered the identification of any biological patterns in the data (Figure 2A). After applying ComBat, the batch effect had drastically diminished, from a silhouette score of 0.28 on the PCA plot (Figure 2A) to −0.05 after correction (Figure 2D).

![Batch effect exploration.](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/m_jjae197_fig2.jpeg?Expires=1779271534&Signature=sDdWryJbueQQa985qNnhvWoVdsk0nd6Qeb1YnzD28XouQXHQch4ZCWBkkTIjOsz1FC0ZiMGVQtxEZLiiNEG~bANCvk55l~YFko3pH0wB8a28Vl5um5L6chVdNEefOVMgczBxDuefk53sNN6E-Wl0nEoZG~tdgJCFhFowXhe3qeFYbM67ylAY~T7tN6p-nUBiIP8j3GGeMoGF1o-TY4vGlzFdXLLsbW7OEyrrg16HQNsLAjwA-gVKQL~olfeJF2tT4CYmVzmzUPDWLaKEGUWPRBENcM8eyvz8r4sHFapo6bPd0QMuZNRdQIsoe8sPRXNL1UrH5QYiVCGRhTcLQ11QQw__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)

Figure 2.

First row: PCA of the first 2 components of the transcriptomics samples, colored by batch (A), tissue (B), and diagnosis (C). Second row: PCA of the first 2 components of the transcriptomics samples after correcting for batch effect using batch variance and pyComBat, colored by batch (D), tissue (E), and diagnosis (F).

[Open in new tab](https://academic.oup.com/view-large/figure/505279322/jjae197_fig2.jpg) [Download slide](https://academic.oup.com/DownloadFile/DownloadImage.aspx?image=https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_fig2.jpeg?Expires=1779271534&Signature=at-vM9jR20EaXXfZsBa3jPhmhoaVIgcq4hcWIiFbtPTq8UZzsXSuauIRdDBgIJI43YnSLDskQc-eIWLY9MYLXrTeTw1C7m-K~euasavTeZZghdAwPH5~kTnSqjMAKTrBQyxIb3-7a8x8Ckrv8ON5Cyy9IN7lV9Ln-uuS2qquEER-2g52i8yeKLXVG2ojH3Fw0kYdKEC3pyQ04Q0Pgd4H9Tolfnc6CCvyjUN4WoYnzhTI4Uz~nJqOx4idK18MKfO0maLojjfSGWKEYZsQp2yYpzTLv-DdHOtgSZ4~GZcoEkC32dhrhAhuINvQjjHsuwHLdYJeFhn9TI2cV1Q~i8PAew__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA&sec=505279322&ar=7942687&xsltPath=~/UI/app/XSLT&imagename=&siteId=5398)

This is further corroborated by calculating the Mutual Information (MI) scores <sup>24</sup> between the features and the batch. Prior to batch correction, 22.28% of the transcriptomics features had MI scores above 0.2; afterward, this percentage dropped to 3.55% ([Figure S5](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)). After correcting the batch effect, the PCA revealed a slight association between the samples and tissue (Figure 2E), which is expected given that transcription patterns are known to be tissue-specific,<sup>21</sup> and most of the samples in the dataset are derived from colon and small intestine. Lastly, other variables, such as diagnosis, do not show an apparent association in the PCA (Figure 2C and F).

### 3.2. Multi-omics signatures can accurately differentiate between CD and UC patients

We explored the differences between UC and CD by training an ML model to classify both diseases using multi-omics data from each sample as an input. The ML classifier was able to distinguish between the 2 indications (Accuracy: 0.77 ± 0.02, Precision (CD): 0.77 ± 0.02; Recall (CD): 0.87 ± 0.02; Precision (UC): 0.75 ± 0.02; Recall (UC): 0.57 ± 0.02; AUC: 0.75 ± 0.02) (Figure 3A and B). These results demonstrate that a multi-omics classifier can accurately distinguish between the 2 phenotypes.

![Machine Learning model performance.](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/m_jjae197_fig3.jpeg?Expires=1779271534&Signature=lepBYyia2FuFPqezXQa-0woiiDqkiuhHlKYpHdAQGOdiXpZFYjGb6SRqhMzCwWxoBzKy2g6WRQEAeC0zo6xDvY9vRFp7KEgXF-h2OV6XrEbuDDTisWaMTOq4qaJT6l16WsxPUp92KvMDw5-4lk9nJ4CRXXVRoS1e9oB1kT7412hCq7k8CUggvqM6VTTw-NZDcUwb~pX1dBElNujPr8kJlq6JQ-3wDyKj8N-Br5QQVfLEep1mVH7hMp-BwT2EFTcbpfRZZDBwpWl2ze30xVKK7VMRwou9bvrK933WUv39lDiEHoK~~WIvJQdy9DV71JY2YQs-wJzlwX9merz9Aziigw__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)

Figure 3.

(A) Confusion matrix of the predictions on the test set of 1 of the 5 cross-validations (CVs) of the model. (B) Bar plots with different performance metrics and the standard deviation of the classifier over the 5 CVs evaluated on the test set. Performance is close to 0.8 across all metrics evaluated. (C) Top 10 most predictive features in the three omics.

[Open in new tab](https://academic.oup.com/view-large/figure/505279326/jjae197_fig3.jpg) [Download slide](https://academic.oup.com/DownloadFile/DownloadImage.aspx?image=https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_fig3.jpeg?Expires=1779271534&Signature=2MAYRSCu0vNYWblQE6~7mOlBUxsJwhU3kdLZUfC5NsSN-Zi0Gt5B8mX-icyEeOEZvmlI-bjLCl8ETMK-6a5xB6s9iIaWq0u4fzX6G~aY0U~BcjybQ0Wg3VcERxMVMP1Jy5CgSTZBRSy1XvRS9LcJpmrZig2LFdNjzIRnaupjweuxu9ivFFTzgdf3HrtMSjQGlqSRk3vzuQ6~GBf0zxlSobrs1MR378q6jcFqInF0AKNo8DVqfBgUm--Jzf~J4Mo7wvowd17CfKAyt1x4yglF3LT4No4syRJ42mWXAakoW1Jh8r6wS~gwc-rqKDVzenaDjN9n~-Wdvwb3zeN9Zb6xkQ__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA&sec=505279326&ar=7942687&xsltPath=~/UI/app/XSLT&imagename=&siteId=5398)

When looking into the most predictive features, we observed a few that stood out from the rest (Figure 3C). Particularly for transcriptomics, there are several known genes associated with inflammation, such as Immunoglobulin Kappa Variable 6D-21 (IGKV6D-21),<sup>25</sup> GALNT6 <sup>26</sup> TBX3,<sup>27</sup> NRG4 <sup>28</sup> and USP38.<sup>29</sup> The function of these genes varies—IGKV6D-21 has been connected with ischemic stroke and IBD, GALNT6 has been shown to intervene in the NF-κB/NLRP3/GSDMD and GSDME pathways, both related to IBD, NRG4 was linked to endothelial inflammation, and USP38 has been linked to inflammation in the heart. However, our results also revealed that a few of them have not yet been clearly linked with IBD or any of its 2 phenotypes (UC and CD), such as RPS26 and TMEM25, suggesting they could be novel genes involved in the pathogenesis of these phenotypes. Similarly, FNDC1 has previously been linked to IBD, but not to specific subtypes.<sup>30</sup>

In the case of proteomics, which is measured in plasma, the top proteins ranked by importance are involved in cardiometabolic or inflammatory processes, and most of them are reported to be linked with IBD. For example, INSL5, together with other anti-inflammatory cytokines, was reported to differentiate between UC and CD.<sup>31</sup> Similarly, low levels of EGFR are associated with the risk of developing IBD.<sup>32</sup> Furthermore, we find 4 other inflammation-related proteins: IL12B,<sup>33</sup> FGF19,<sup>34</sup> LY96,<sup>35</sup> CCL20,<sup>36</sup> and BCL2,<sup>37</sup> which are associated with disease activity. On the other hand, there are top-ranked proteins that were not previously linked with IBD, such as ANGPTL3. We do not find loci associated with IBD features within the top genomics features.

### 3.3. Identifying molecular profiles that correlate with disease severity in ulcerative colitis

In this subsection, we modeled multi-omics UC samples using MOFA ([Figure S6](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)). Our goal was to leverage this unsupervised technique to pinpoint characteristic molecular profiles that correlate with clinical phenotypes, such as disease severity (based on endoscopy) and macroscopic appearance (ie, whether the sample is inflamed or not). By exploring these multi-omics profiles, we ultimately intend to identify biomarkers that can be used to define patient subpopulations.

By clustering the factors from MOFA, we observed a correlation (*R* <sup>2</sup>) of 0.40 between factor 1 and disease severity (Figures 4A and [S7](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)). The Kendall’s Tau test further corroborates this, showing a moderate yet significant (*P* -value = 8 × 10 <sup>-4</sup>) correlation of 0.30. This correlation suggests that the features associated with this factor can potentially be used to distinguish between patients with severe or moderate disease and patients with mild disease or in remission. Thus, we investigated the top 150 features across the 3 omics based on their weights for this factor since these top features are responsible for the variability observed within this factor. To identify features associated with severe disease, we applied ANOVA to proteomic and transcriptomic features and chi-square tests to genomic features, comparing severe cases with others. *P* -values were adjusted for multiple comparisons using the Benjamini–Hochberg method (adjusted *P*  <.05).

![MOFA model for UC.](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/m_jjae197_fig4.jpeg?Expires=1779271534&Signature=bIs4VtwOOt7b6VZrQ0lcNw34mef3JIDiYpTq9gff94KzS-WeUL7FI7i1zKkO9aL-lpuFra-B~0iuPpSlVytbWTQfSFU6lCTCVG03q9ad5vCwfirBTWYVWQr2xbEd4cMtAtiSpZd~TCaYfZkufumE1JkjjMe2RpNGFYNjuE1iw95IwTSxgDA692Yqri6Vygjq0Du6ugNid1znQ8KhBgJM2faDD-7fCTkUWrJHWsCOTciuhjq93wCIebcHLpTra~qD3DuZNizzSIDfw1RvZhnrdnjyzs9aqJEZuyPZIGu3s7Ao0v7bQWFvYR4hTpzndsyJ-Ex-YDxlXCLo1rugWxc~Vg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)

Figure 4.

(A) Distribution of the absolute factor 1 values stratified by disease severity based on endoscopy. The correlation between factor 1 and disease severity is 0.4 considering mild = 1, moderate = 2, severe = 3 to make disease severity a numeric variable. (B) Distribution of the expression values for IL17A (proteomics). (C) Top 10 enriched pathways using the significant proteomics features (orange). (D) Distribution of the expression values for TGFA (proteomics). (E) Top 10 enriched pathways using the significant transcriptomics features (green). (F) Distribution of the expression values for DLD (transcriptomics).

[Open in new tab](https://academic.oup.com/view-large/figure/505279332/jjae197_fig4.jpg) [Download slide](https://academic.oup.com/DownloadFile/DownloadImage.aspx?image=https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_fig4.jpeg?Expires=1779271534&Signature=T1sQQ4wVJUdvfuEeft3~Xh-IIx8mYtChdbom4rcu4TYP77X0GrcPy~n46bJdu3RdLM-MxbOTrhmx-j0NL3MO~8cp1GQJnOgGY0zbQnCbVkNyf9N6rYUPJ7ovw70L6vk-MYr3PTZj5d2Uhb6H8lVPyQLnvuSN0NnNHyzgFtNRl07g~Br~u83D9CahWfAxec1GN74x4shq6oI1fiE0rD9OzZLgdnfujA3C5ZdoXgjVPrpU6sU8irj1WAnWzf9dq1QY3niKGIuzEo9FwYzjswiqXgw84OfV5rGLKrZgy1Bp0XB1~-EoJnRUanR8DjpJ9V~CjQhKYy9X2AR1b2mW00glLQ__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA&sec=505279332&ar=7942687&xsltPath=~/UI/app/XSLT&imagename=&siteId=5398)

Among the significant features, we identified several potential biomarkers for disease severity across the 3 omics. For proteomics, we observed that disease severity correlates with IL17A, TGFA (Figure 4B and D), EPO, and REG1B ([Figure S7](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)). Similarly, in transcriptomics, we found several examples, such as DLD, EMILIN2, DPH6, and GRID1, whose response varies with disease severity (Figures 4F and [S7](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)). Lastly, we investigated the enriched pathways of these significant features by running pathway enrichment analysis on each omics modality independently. Among the enriched pathways, we found interleukin and cytokine signaling pathways for proteomics (Figure 4C) and metabolic pathways as well as pathways related to hemostasis and response to pathogens.

### 3.4. Investigating the molecular phenotype of samples in Crohn’s disease reveals 2 subpopulations

Similar to the previous section on UC, we modeled multi-omics CD samples using MOFA aimed at identifying molecular profiles that correlate with clinical phenotypes. As mentioned in Section 2, we modeled colon and small intestine samples separately due to the strong tissue effect. Here, we exclusively report the findings derived from the colon model since we did not find a clear correlation between any clinical variable and factor from the small intestine model.

First, we began by performing hierarchical clustering across all samples based on all factors yielded by MOFA to assess whether any factor was correlated with any variable of clinical interest (Figures 5A and [S8](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)). While the clusters did not reveal a clear correlation with any confounding variables such as batch, sex, and age, we found that factor 3, which has a relevant contribution for more than 1 omics modality and discriminates between inflamed and normal samples ([Figure S9A](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)), in CD, this is more clearly shown when zooming in on factor 3 separately (Figure S9C). Subsequently, we were able to identify a clear correlation with macroscopic appearance (Figure 5B). For this factor, non-inflamed samples exhibit values close to 0. In contrast, the majority of the inflamed samples have either highly positive or highly negative values, suggesting 2 distinct inflammation phenotypes. Notably, individuals with inflamed samples tend to have a higher Simple Endoscopic Score for Crohn’s Disease (SES-CD), suggesting an increased disease severity ([Figure S10](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)).<sup>38</sup>

![MOFA model for CD.](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/m_jjae197_fig5.jpeg?Expires=1779271534&Signature=avK-fDAYy9c-nBoXAFj4UX9H3TMyifQoHAMF3UfSFPplFQDKANwCRiZ~PftWABWWustq6WkmwNMGXl286a~SCnQ691S05QGmc2vw7OzJM1jF3dugDpMzb9MsCdktJPzTRe3Ez4PyGGAmPSKS56~TAplrAt63-UD~iGYpIsPkoGCq6pD~LaTJV8EoISJ9gzJUhdlkLT~zofGth6KbG9pwfTHR3Tgu72WEghcou1KfQybcKhpMr9705Rach4JV--R0pLnGF10yw3zH2kJqI~MlfCEHKeFQ2TwBRIBVt4vGBL8NInMflkyVmmSeGfZMYc4SkIh18Olzn~nqqs7Xr7BToQ__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)

Figure 5.

(A) Hierarchical clustering applied to the factors from Multi-Omics Factor Analysis (MOFA) for multi-omics Crohn’s disease (CD) samples. Transcriptomics and proteomics data are derived from colon and plasma, respectively. Clustering on all factors reveals 3 main clusters. (B) Hierarchical clustering applied exclusively to factor 3 and the reported macroscopic appearance for each sample (inflamed/normal). Samples with extreme values of factor 3 (dark-red and dark-blue) are likely to be inflamed, while values of factor 3 closer to zero (light-red, light-blue, and white) are less likely to be inflamed. (C) Distribution of the factor 3 values for the 2 identified subpopulations (A: cluster 1 and 3, and B: cluster 2) stratified by macroscopic appearance (inflamed/normal). (D–F) Distribution of the expression values for NOS2 (proteomics), IL12B (proteomics), and TSBP1-AS1 (transcriptomics) across the 2 subpopulations (A and B), stratified by macroscopic appearance. The 3 features are an example of an inflammation marker, cluster A specific marker, and cluster B specific marker, respectively. (G) Proportion of HLA genes among the top 150 transcriptomic features in factor 3. (H) Most common genes of the top 150 genomics features (SNPs). TSBP1 SNPs correspond to approximately 30% of the top genomics features. (I) Top 5 enriched pathways using the significant proteomics features for the inflamed cluster A (orange) and significant transcriptomics features for the inflamed cluster B (green). Statistical significance is measured with Mann–Whitney–Wilcoxon test 2-sided (Legend: \*\*\*\* =  *P-* value <.0001; \*\*\* =  *P-* value <.001; \*\* =  *P-* value <.01; \*\* =  *P-* value <.05; ns = nonsignificant).

[Open in new tab](https://academic.oup.com/view-large/figure/505279337/jjae197_fig5.jpg) [Download slide](https://academic.oup.com/DownloadFile/DownloadImage.aspx?image=https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_fig5.jpeg?Expires=1779271534&Signature=JErrDx7QED5rVJb~9tPOFDOnTuXDSbuieHFZmCNFjdLaVh35NKQ73XCXk96KCXNFggq4G3nLF5Wk-bz3onQRNxyeeWR9~wlM5npmFYYtT9EZw9yGXmx2SoRScX2jO5uG4v1idBJL-fxlACrPOZTuN4~Yi~rFHGTCz9HQHWGdsJSr8uQJ4TbDAUxVAWv5t~uo4Eq8nO54kmovMyS4UMhjdrNdd~x91N1U-KXZ3PCHtM4q6iwExfkO92KuwE~20qB5lhPu0BoaHzSa7zJxFSsCHo~HXHfGJi3uvVT-g9QCRkHnDgpJiK0VtI-wTZmNAum5Sjh5D1EYFpEdEnwmRY72jg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA&sec=505279337&ar=7942687&xsltPath=~/UI/app/XSLT&imagename=&siteId=5398)

After revealing the association between factor 3 and macroscopic appearance, we explored the distribution of factor 3 values across the 3 main identified clusters derived from the MOFA factors (Figure 5B). Stratifying by the 3 clusters again suggests 2 subpopulations of inflamed samples, 1 comprising inflamed samples in clusters 1 and 3 (both present high negative factor 3 values) and 1 containing the inflamed samples of cluster 2 (positive factor 3 values). Therefore, we subsequently combined the inflamed samples of clusters 1 and 3 as they manifest a similar inflammation pattern based on factor 3. From this point on, the aggregate of clusters 1 and 3 is referred to as cluster A and cluster 2 as cluster B (Figure 5C).

Next, we explored the top 150 features in each omics modality based on the absolute weights of factor 3. Our goal here was 2-fold: (1) identify which of these features can distinguish between inflamed and not inflamed samples and thus can be used as inflammation markers, and (2) investigate the different molecular signatures between the 2 potential subpopulations identified for inflamed samples. Among the top features in factor 3, we found several markers, both up- and downregulated, in proteomics/transcriptomics that differentiates between inflamed and normal, such as CXCL9, HLA-DRA, INHBB, SERPINA3, and NOS2 (Figures 5D and [S11](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)). All of these proteomics or transcriptomics features have potential use as biomarkers for intestinal inflammation in the context of CD.

Similarly, to identify features distinguishing the 2 inflamed sample subpopulations, we applied ANOVA to the top 150 proteomic and transcriptomic features and chi-square tests to the top genomic features, using clusters as groups. *P* -values were adjusted for multiple comparisons using the Benjamini–Hochberg method (adjusted *P*  <.05). This revealed a subset of features characterizing the 2 subpopulations (Figure 5E and F). When investigating the transcriptomics features characteristic of cluster B, we found a large majority of these transcripts were Human Leukocyte Antigen (HLA) genes (Figure 5G), a set of genes responsible for the regulation of the immune system and involved in antigen processing and presentation ([Figure S12](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1779271534&Signature=4CTyyboztx6BU5ndQixrExEHuDMPgand4Y-gHcV1gNZAFC8i3Xu13S8n-gDFX2E9nxt~NcbkC1LYYVPuTcoeIi4UQ10JIbAow9FHCl26d5gWZvfaXfjXOI6sGO4a0L3Lr-HIBfQPnyoEShPGJHyMOK0EL91XiKroDpVRCk7jxPUwryPlhZ38LIVflxgauif2UCJwcp1c8ZZZXvafFijo~nKfy5yUPA97FMTCeRotG4mHKH509C6fVgj-qfAiIX1UMb-WOHLH7AbZuuqDy0DVsP1~oU6R1SipujkqWmoxhJvfnVHlO5uWQ4mfygzFq5bg5gd-MvTN~PNXCf6dGkJlUg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)). Furthermore, we found that one of the transcripts characteristic to cluster B, TSBP1-AS1 (Figure 5F), corresponds to the most occurring single nucleotide polymorphisms (SNPs) highlighted in genomics, as 41 SNPs of this gene appear in the top 150 genomics features (Figure 5H). As a reference, there are 361 SNPs for this gene in the total 166 916 SNPs analyzed. In other words, while the SNPs of this gene represent 0.2% of the genomics features, it is over-represented among the top 150 genomics features in factor 3 with ~27%. The SNPs of this antisense noncoding RNA (ncRNA) are also located in the HLA region in chromosome 6, suggesting an association between these SNPs and the regulation of HLA genes. Cluster A, on the other hand, presented a smaller number of characteristic features. One of them is the IL12B in proteomics (Figure 5E), a cytokine that acts on T and natural killer cells and is upregulated in cluster A.

Lastly, we investigated the pathways enriched using the characteristic features of the 2 inflamed subpopulations. Among the enriched pathways for proteomics, we found several inflammation-related pathways related to the innate immune system for cluster A (eg, natural killer proliferation and activation) (Figure 5I). In the case of transcriptomics pathways for cluster B, we observed pathways related to antigen processing and presentation, immunoglobulin production, and the MHC class. Our results suggest that the differentiation between these 2 subpopulations of inflamed samples is due to cluster B developing a more robust or heightened adaptive immune response characterized by high expression of HLA genes and other inflammation-related pathways.

## 4\. Conclusion

In this study, we conducted a multi-omics analysis on samples from a large IBD patient cohort to identify distinct patient subgroups. We first assessed whether an ML classifier could accurately distinguish between UC and CD samples by exclusively training it on multi-omics data. The performance of the model indicates that multi-omics can be used to accurately predict samples between the 2 conditions. Furthermore, we leveraged the interpretability of the model used to investigate its most predictive omics features. As expected, a large proportion of them have been previously reported in the literature and associated with either of the indications, thus serving as a control on the method. However, others have not yet been linked with IBD and should be investigated further as they might play a role in the pathophysiology of the disease and could be used as biomarkers for diagnosing patients with indeterminate colitis.

In parallel, we delved deeper into each IBD subtype—CD and UC—by categorizing patients into subgroups using MOFA. This exploration unveiled distinct subpopulations within each disease category, offering promising avenues for the application of precision medicine strategies. Interestingly, a few omics signatures appear to be mainly responsible for said separation. Among these omics, we found previously associated markers with IBD, such as IL17A, SERPINA3, and CXCL9, as well as novel genes such as TSBP1-AS1 and ZNF268. We compared the identified features with those reported in other studies <sup>39–42</sup> to facilitate conducting meta-analyses as well as pinpointing potentially novel biomarkers ([Supplementary Data](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_data.xlsx?Expires=1779271534&Signature=Zm2hMKEJ2bWstpbzoMPvKaVR17TBzJQdhTA6kGZwwnO8RQ7R32qyVKjtPs9T60CI2i~jS-QfJL-KCJGroTWUSv32WkLZHWPJAglrMVZcmYm9DcEnsdjQakRpmbvZ5t5CHPOTWurMuvSMkKb3s~LO5Ryuc9859ELXmjSZuSSPCD7h-0YQI7Rw4KYubYo7mc2PDGtDsMDLMP-jv-xHZvd6ggLDCiyHbC8tNpRdbsC8SHpRe5ttIrmlH~P6NFFLozcI8BTnLUu~eQtTNyYiJfovsSelRGKj2f-XeYzG4JrP0zBDM0OO47v-Lpo5WmoaVcnPv0TrXEXFAWf9UtxmDOQF8Q__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)). To summarize, our findings lay the groundwork for further research into the molecular underpinnings of IBD and highlight the potential for tailored therapeutic interventions based on specific omics profiles.

Several limitations must be acknowledged in the present study. First, the absence of comprehensive omics data for all samples constrained the effective sample size, limiting our analysis’s breadth. Second, the ML classifier employed demonstrates significant accuracy in distinguishing between patient groups based on omics profiles; however, the performance is lower for UC. We also acknowledge the potential risk of overfitting due to the significantly higher number of features compared to the number of samples. However, performing complex dimensionality reduction could hinder our ability to retrieve clear biomarker information, which is a key objective of this study. XGBoost includes several mechanisms that mitigate this risk, such as regularization (L1 and L2) and tree pruning, which help to penalize overly complex models. Additionally, XGBoost employs techniques like subsampling of features and data during training, reducing the likelihood of fitting to noise. Nonetheless, we acknowledge that balancing model complexity and interpretability remains a challenge. Finally, despite this study representing one of the largest patient-level investigations into IBD to date, the sample size could still benefit from expansion to enhance the robustness and generalizability of our findings.

In the future, we envision several potential extensions of our work. First, we aim at investigating additional omics modalities beyond the three analyzed to increase the breadth of molecular coverage and ultimately uncover new biological insights. To achieve this, untargeted LC-MS- and NMR-based metabolomics should be performed to add an extra layer of biology. Additionally, we aim to integrate transcriptomics data from multiple tissue types when training a classifier. Another potential clinical application is using the most predictive features of the ML model as a minimal set of discriminative features and assessing whether they alone can accurately discriminate between IBD subtypes. Finally, the strategy to address the missing values needs to be revisited with a less conservative approach, such that we do not simply use only the samples with all omics types available. We intend to re-assess our findings as patients in the SPARC cohort continue to be phenotyped. Additionally, it is necessary to confirm these findings in independent cohorts to ensure their generalizability. The performance of the ML model would also likely benefit from the aforementioned steps.

To summarize, our work identified biomarkers that (1) can distinguish between CD and UC and (2) can distinguish between distinct IBD subpopulations: UC patients with higher versus lower disease severity and CD patients with distinct types of inflammation. Our findings will have a significant impact on clinical practice as they enable the identification of relevant patient subpopulations for which personalized treatment regimes can be developed.

## Acknowledgments

We would like to acknowledge Dr. David Healey and Dr. Biswapriya B. Misra for their thoughtful comments and feedback on the manuscript. The results published here are in whole from the Study of a Prospective Adult Research Cohort with IBD (SPARC IBD). SPARC IBD is a component of the Crohn’s & Colitis Foundation’s IBD Plexus data exchange platform. SPARC IBD enrolls patients with an established or new diagnosis of IBD from sites throughout the United States and links data collected from the electronic health record and study-specific case report forms. Patients also provide blood, stool, and biopsy samples at selected times during follow-up. The design and implementation of the SPARC IBD cohort has been previously described.

## Author contributions

A.J.P., D.D.F., and K.A.W. designed the study. A.J.P., S.C., and D.E. prepared the datasets. A.J.P. analyzed the datasets. A.P.J. and D.D.F. made the figures. A.J.P., M.H., D.D.F., and K.A.W. interpreted the results. A.J.P. and D.D.F. wrote the paper with help from K.A.W. All authors reviewed the manuscript. All authors have read and approved the final manuscript.

## Funding

None declared.

## Conflicts of interest

All authors were employees of Enveda Inc. during the course of this work and have real or potential ownership interest in the company.

## Data and code availability

SPARC IBD is available upon approved application to Crohn’s & Colitis Foundation IBD Plexus ([https://www.crohnscolitisfoundation.org/ibd-plexus](https://www.crohnscolitisfoundation.org/ibd-plexus)). We released the scripts and notebooks to reproduce the work at [https://github.com/enveda/sparc-multiomics](https://github.com/enveda/sparc-multiomics).

## References

Weersma

RK

,

Xavier

RJ

,

Vermeire

S

,

Barrett

JC

;

IBD Multi Omics Consortium

..

Gastroenterol.

2018

;

155

:

e1

–

e4

. https://doi.org/

[10.1053/j.gastro.2018.07.039](https://doi.org/10.1053/j.gastro.2018.07.039)

Lloyd-Price

J

,

Arze

C

,

Ananthakrishnan

AN

, et al.;

IBDMDB Investigators

..

Nature.

2019

;

569

:

655

–

662

. https://doi.org/

[10.1038/s41586-019-1237-9](https://doi.org/10.1038/s41586-019-1237-9)

Agrawal

M

,

Allin

KH

,

Petralia

F

,

Colombel

JF

,

Jess

T.

.

Nat Rev Gastroenterol Hepatol.

2022

;

19

:

399

–

409

. https://doi.org/

[10.1038/s41575-022-00593-y](https://doi.org/10.1038/s41575-022-00593-y)

Subramanian

I

,

Verma

S

,

Kumar

S

,

Jere

A

,

Anamika

K.

.

Bioinf Biol Insights.

2020

;

14

:

1

. https://doi.org/

[10.1177/1177932219899051](https://doi.org/10.1177/1177932219899051)

Sudhakar

P

,

Alsoud

D

,

Wellens

J

, et al..

J Crohns Colitis.

2022

;

16

:

1306

–

1320

. https://doi.org/

[10.1093/ecco-jcc/jjac027](https://doi.org/10.1093/ecco-jcc/jjac027)

Imhann

F

,

Van der Velde

KJ

,

Barbieri

R

, et al..

BMC Gastroenterol.

2019

;

19

:

1

–

10

. https://doi.org/

[10.1186/s12876-018-0917-5](https://doi.org/10.1186/s12876-018-0917-5)

Raffals

LE

,

Saha

S

,

Bewtra

M

, et al..

Inflamm Bowel Dis.

2022

;

28

:

192

–

199

. https://doi.org/

[10.1093/ibd/izab071](https://doi.org/10.1093/ibd/izab071)

Mo

S

,

Jin

B

,

Tseng

Y

, et al..

J Transl Med.

2023

;

21

:

466

. https://doi.org/

[10.1186/s12967-023-04326-w](https://doi.org/10.1186/s12967-023-04326-w)

Janker

L

,

Schuster

D

,

Bortel

P

, et al..

J Crohns Colitis.

2023

;

17

:

1514

–

1527

. https://doi.org/

[10.1093/ecco-jcc/jjad052](https://doi.org/10.1093/ecco-jcc/jjad052)

Motwani

KK

,

Alizadeh

M

,

Abutaleb

A

,

Grossman

J

,

Wellington

J

,

Cross

RK.

.

Dig Dis Sci.

2024

;

69

:

2154

–

2163

. https://doi.org/

[10.1007/s10620-024-08421-w](https://doi.org/10.1007/s10620-024-08421-w)

Muzellec

B

,

Teleńczuk

M

,

Cabeli

V

,

Andreux

M.

.

J. Bioinform.

2023

;

39

:

btad547

. https://doi.org/

[10.1093/bioinformatics/btad547](https://doi.org/10.1093/bioinformatics/btad547)

Behdenna

A

,

Colange

M

,

Haziza

J

, et al..

BMC Bioinf.

2023

;

24

:

459

. https://doi.org/

[10.1186/s12859-023-05578-5](https://doi.org/10.1186/s12859-023-05578-5)

Ritchie

ME

,

Phipson

B

,

Wu

DI

, et al..

Nucleic Acids Res.

2015

;

43

:

e47

–

e47

. https://doi.org/

[10.1093/nar/gkv007](https://doi.org/10.1093/nar/gkv007)

Danecek

P

,

Auton

A

,

Abecasis

G

, et al.;

1000 Genomes Project Analysis Group

..

J. Bioinform.

2011

;

27

:

2156

–

2158

. https://doi.org/

[10.1093/bioinformatics/btr330](https://doi.org/10.1093/bioinformatics/btr330)

Martin

FJ

,

Amode

MR

,

Aneja

A

, et al..

Nucleic Acids Res.

2023

;

51

:

D933

–

D941

. https://doi.org/

[10.1093/nar/gkac958](https://doi.org/10.1093/nar/gkac958)

Chen

T

,

Guestrin

C.

.

Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining.

2016:

785

–

794

. https://doi.org/

[10.1145/2939672.2939785](https://doi.org/10.1145/2939672.2939785)

Nielsen

RL

,

Monfeuga

T

,

Kitchen

RR

, et al..

Nat Commun.

2024

;

15

:

2817

. https://doi.org/

[10.1038/s41467-024-46663-4](https://doi.org/10.1038/s41467-024-46663-4)

Argelaguet

R

,

Velten

B

,

Arnol

D

, et al..

Mol Syst Biol.

2018

;

14

:

e8124

. https://doi.org/

[10.15252/msb.20178124](https://doi.org/10.15252/msb.20178124)

Selin

KA

,

Hedin

CR

,

Villablanca

EJ.

.

J Crohns Colitis.

2021

;

15

:

1959

–

1973

. https://doi.org/

[10.1093/ecco-jcc/jjab085](https://doi.org/10.1093/ecco-jcc/jjab085)

Figueiredo

RQ

,

Del Ser

SD

,

Raschka

T

, et al..

BMC Bioinf.

2022

;

23

:

231

. https://doi.org/

[10.1186/s12859-022-04765-0](https://doi.org/10.1186/s12859-022-04765-0)

Fang

Z

,

Liu

X

,

Peltz

G.

.

J. Bioinform.

2023

;

39

:

btac757

. https://doi.org/

[10.1093/bioinformatics/btac757](https://doi.org/10.1093/bioinformatics/btac757)

Chen

EY

,

Tan

CM

,

Kou

Y

, et al..

BMC Bioinf.

2013

;

14

:

1

–

14

. https://doi.org/

[10.1186/1471-2105-14-128](https://doi.org/10.1186/1471-2105-14-128)

Yu

X

,

Xu

X

,

Zhang

J

,

Li

X.

.

Nat Commun.

2023

;

14

:

960

. https://doi.org/

[10.1038/s41467-023-36635-5](https://doi.org/10.1038/s41467-023-36635-5)

Hu

W

,

Li

P

,

Zeng

N

,

Tan

S.

.

Sci Rep.

2023

;

13

:

1741

. https://doi.org/

[10.1038/s41598-023-27459-w](https://doi.org/10.1038/s41598-023-27459-w)

Ding

M

,

Liu

J

,

Lv

H

, et al..

Front Oncol.

2023

;

1097

:

772

. https://doi.org/

[10.3389/fonc.2023.1097772](https://doi.org/10.3389/fonc.2023.1097772)

Khan

SF

,

Damerell

V

,

Omar

R

, et al..

Gene.

2020

;

726

:

144223

. https://doi.org/

[10.1016/j.gene.2019.144223](https://doi.org/10.1016/j.gene.2019.144223)

Shi

L

,

Li

Y

,

Xu

X

, et al..

Nat Metab.

2022

;

4

:

1573

–

1590

. https://doi.org/

[10.1038/s42255-022-00671-0](https://doi.org/10.1038/s42255-022-00671-0)

Gong

Y

,

Yu

T

,

Shuai

W

,

Chen

T

,

Zhang

J

,

Huang

H.

.

Mol Med.

2023

;

29

:

157

. https://doi.org/

[10.1186/s10020-023-00750-2](https://doi.org/10.1186/s10020-023-00750-2)

Wuensch

T

,

Wizenty

J

,

Quint

J

, et al..

Gastroenterol Res Pract

.

2019

;

2019

:

3784172

. https://doi.org/

[10.1155/2019/3784172](https://doi.org/10.1155/2019/3784172)

Skok

DJ

,

Hauptman

N

,

Jerala

M

,

Zidar

N.

.

Genes.

2021

;

12

:

1477

. https://doi.org/

[10.3390%2Fgenes12101477](https://doi.org/10.3390%2Fgenes12101477)

Yang

Y

,

Ludvigsson

JF

,

Olén

O

,

Sjölander

A

,

Carrero

JJ.

.

Inflamm Bowel Dis.

2024

;

30

:

718

–

725

. https://doi.org/

[10.1093%2Fibd%2Fizac267](https://doi.org/10.1093%2Fibd%2Fizac267)

Lee

HW

,

Chung

SH

,

Moon

CM

, et al..

Medicine (Baltimore).

2016

;

95

:

e3772

. https://doi.org/

[10.1097/md.0000000000003772](https://doi.org/10.1097/md.0000000000003772)

Łukawska

A

,

Mulak

A.

.

Adv Clin Exp Med.

2024

. https://doi.org/

[10.17219/acem/184132](https://doi.org/10.17219/acem/184132)

Bank

S

,

Skytt Andersen

P

,

Burisch

J

, et al..

PLoS One.

2014

;

9

:

e98815

. https://doi.org/

[10.1371/journal.pone.0098815](https://doi.org/10.1371/journal.pone.0098815)

Kaser

A

,

Ludwiczek

O

,

Holzmann

S

, et al..

J Clin Immunol.

2004

;

24

:

74

–

85

. https://doi.org/

[10.1023/B:JOCI.0000018066.46279.6b](https://doi.org/10.1023/B:JOCI.0000018066.46279.6b)

Weder

B

,

Mozaffari

M

,

Biedermann

L

, et al..

Clin Exp Immunol.

2018

;

193

:

346

–

360

. https://doi.org/

[10.1111/cei.13151](https://doi.org/10.1111/cei.13151)

Daperno

M

,

D’Haens

G

,

Van Assche

G

, et al..

Gastrointest Endosc.

2004

;

60

:

505

–

512

. https://doi.org/

[10.1016/S0016-5107(04)01878-4](https://doi.org/10.1016/S0016-5107\(04\)01878-4)

Jiang

L

,

Zhang

S

,

Jiang

C

, et al..

Sci Rep.

2024

;

14

:

24290

. https://doi.org/

[10.1038/s41598-024-75797-0](https://doi.org/10.1038/s41598-024-75797-0)

Kalla

R

,

Adams

AT

,

Nowak

JK

, et al.;

IBD-Character Consortium

..

J Crohns Colitis.

2023

;

17

:

170

–

184

. https://doi.org/

[10.1093/ecco-jcc/jjac127](https://doi.org/10.1093/ecco-jcc/jjac127)

Verstockt

B

,

Verstockt

S

,

Cremer

J

, et al..

BMJ Open Gastroenterology.

2023

;

10

:

e001003

. https://doi.org/

[10.1136/bmjgast-2022-001003](https://doi.org/10.1136/bmjgast-2022-001003)

Czarnewski

P

,

Parigi

SM

,

Sorini

C

, et al..

Nat Commun.

2019

;

10

:

2892

. https://doi.org/

[10.1038/s41467-019-10769-x](https://doi.org/10.1038/s41467-019-10769-x)

## Author notes

Daniel Domingo-Fernández and Kiana A West contributed equally to this work.

## Supplementary data

[jjae197\_suppl\_Supplementary\_File](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_file.docx?Expires=1780783998&Signature=X9BxZucZ5dYlzPrurVvyoyfpVNW6948KV73G9DTf6HZu8cWVu~S7uajJT12pK6FiMTDuZrplkKRKCYoD2h2kyz7QbidTQIZ4RR9U0FRio-bkXJuPAOErtYDOhpNDXGEki4aonvBXVrgrNICoUrddI3LVpLXv~JugQ1kCKA9dhGKZl4l-tFI4C6BFAdC6ClHeYYFGqd2~d-WIL3P-etCEHKOQbOSOFbciOuqBkgpwJKfZn4KwhNacxv4mUy4-TuBZXNeMo~okE4usytopq-f73h2IoDYmVwrjgNlbWu5FQlXsbg7SwUZ1f-knsmCX4Cis~AuJJ11zVfcqil33s28sGA__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA) - docx file

[jjae197\_suppl\_Supplementary\_Data](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/19/1/10.1093_ecco-jcc_jjae197/2/jjae197_suppl_supplementary_data.xlsx?Expires=1780783998&Signature=gtkUfqungvHaJWyD6RJCACae39j9IBMvNmFCvTs42dOWICvvFH7GaEuB42AfNrl8Orjj2FRdTthcVuXrG7XLWNGMimziMWx27AeHba~UFbnx4tMtKgKhKQ0Jh7-CgkYI4yPT-E3LIkznuKI2KYpNxMlsTKYFNRavGuMFlg6maWALGYMk4LaK1Qys-AZ4kbS0-CB5YWTfaccRR9zAu9AL9K3IlZBAUKxv1FHeOZec69E-txcXEu4MoDR6EYWa8oZmTEc1vAIWRWzpNVA7WakuYycZBm0OBtkWetVBERX~9GF1A5YwMeMdwmvMvbVfbwrPNGeAVpOW0JfTn3dmEH29VQ__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA) - xlsx file