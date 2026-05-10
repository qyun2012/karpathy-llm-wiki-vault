---
title: "Multi-omics reveal microbial determinants impacting responses to biologic therapies in inflammatory bowel disease"
source: "https://www.cell.com/cell-host-microbe/fulltext/S1931-3128(21)00301-2?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS1931312821003012%3Fshowall%3Dtrue"
author:
  - "[[Jonathan Wei Jie Lee]]"
  - "[[Damian Plichta]]"
  - "[[Larson Hogstrom]]"
  - "[[Nynke Z. Borren]]"
  - "[[Helena Lau]]"
  - "[[Sara M. Gregory]]"
  - "[[William Tan]]"
  - "[[Hamed Khalili]]"
  - "[[Clary Clish]]"
  - "[[Hera Vlamakis]]"
  - "[[Ramnik J. Xavier]]"
  - "[[Ashwin N. Ananthakrishnan]]"
published: 2020-12-15
created: 2026-05-06
description: "Biomarkers predicting responses and guiding stratified therapeutic approaches in inflammatorybowel disease (IBD) remain an unmet medical need. Lee et al. identified fecal metagenomic,serum metabolomic, and proteomic markers that predict differential response to eitheranti-cytokine or anti-integrin therapy in IBD."
tags:
  - "clippings"
---
## Summary

The intestinal microbiome is a key determinant of responses to biologic therapy in inflammatory bowel disease (IBD). However, diverse therapeutics and variable responses among IBD patients have posed challenges in predicting clinical therapeutic success. In this prospective study, we profiled baseline stool and blood in patients with moderate-to-severe Crohn's disease or ulcerative colitis initiating anti-cytokine therapy (anti-TNF or -IL12/23) or anti-integrin therapy. Patients were assessed at 14 weeks for clinical remission and 52 weeks for clinical and endoscopic remission. Baseline microbial richness indicated preferential responses to anti-cytokine therapy and correlated with the abundance of microbial species capable of 7α/β-dehydroxylation of primary to secondary bile acids. Serum signatures of immune proteins reflecting microbial diversity identified patients more likely to achieve remission with anti-cytokine therapy. Remission-associated multi-omic profiles were unique to each therapeutic class. These profiles may facilitate *a priori* determination of optimal therapeutics for patients and serve as targets for newer therapies.

## Graphical abstract

![Graphical abstract undfig1](https://www.cell.com/cms/10.1016/j.chom.2021.06.019/asset/6acd807c-c02b-46a3-886e-2293b8a0fac1/main.assets/fx1_lrg.jpg)

Graphical abstract undfig1

## Introduction

Inflammatory bowel disease (IBD), which includes Crohn’s disease (CD) and ulcerative colitis (UC), affects nearly 3 million individuals in the United States (

3.

Ananthakrishnan, A.N. ∙ Kaplan, G.G. ∙ Ng, S.C.

**Changing Global epidemiology of inflammatory bowel diseases: sustaining health care delivery into the 21st century**

*Clin. Gastroenterol. Hepatol.* 2020; **18**:1252-1260

;

24.

Graham, D.B. ∙ Xavier, R.J.

**Pathway paradigms revealed from the genetics of inflammatory bowel disease**

*Nature.* 2020; **578**:527-539

). The availability of therapies with diverse mechanisms of action inhibiting leukocyte trafficking (anti-integrins) or blocking the effect of inflammatory cytokines (anti-tumor necrosis factor, anti-interleukin \[IL\] 12/23) (

15.

Danese, S. ∙ Vuitton, L. ∙ Peyrin-Biroulet, L.

**Biologic agents for IBD: practical insights**

*Nat. Rev. Gastroenterol. Hepatol.* 2015; **12**:537-545

) have revolutionized our ability to achieve clinical remission and endoscopic healing, thereby preventing disease-related morbidity. However, despite an initial response, only a small proportion of patients achieve sustained remission. In addition, a critically important limitation of the existing therapeutic paradigm is the need for sequential trials of different therapeutic classes upon failure of previous therapy (

38.

Plichta, D.R. ∙ Graham, D.B. ∙ Subramanian, S....

**Therapeutic opportunities in inflammatory bowel disease: mechanistic dissection of host-microbiome relationships**

*Cell.* 2019; **178**:1041-1056

). The inability to *a priori* define the medication most likely to benefit a patient introduces a potential delay in achieving remission, reduces the rate of response, and leads to protracted morbidity. Thus, understanding the determinants of response to one or more therapeutic classes is of paramount scientific and clinical importance. In observational cohorts and randomized controlled trials, clinical parameters alone have insufficient predictive value in determining response to a therapeutic class and there has been no robust development of models that may predict differential response to different mechanisms of action.

The intestinal microbiome is central to the pathogenesis of CD and UC (

23.

Gevers, D. ∙ Kugathasan, S. ∙ Denson, L.A....

**The treatment-naive microbiome in new-onset Crohn’s disease**

*Cell Host Microbe.* 2014; **15**:382-392

;

33.

Lloyd-Price, J. ∙ Arze, C. ∙ Ananthakrishnan, A.N....

**Multi-omics of the gut microbial ecosystem in inflammatory bowel diseases**

*Nature.* 2019; **569**:655-662

;

42.

Schirmer, M. ∙ Denson, L. ∙ Vlamakis, H....

**Compositional and temporal changes in the gut microbiome of pediatric ulcerative colitis patients are linked to disease course**

*Cell Host Microbe.* 2018; **24**:600-610.e4

). Diversion of the fecal stream with an ileostomy effectively ameliorates downstream inflammation in the colon (

41.

Rutgeerts, P. ∙ Goboes, K. ∙ Peeters, M....

**Effect of faecal stream diversion on recurrence of Crohn’s disease in the neoterminal ileum**

*Lancet.* 1991; **338**:771-774

). A less diverse microbiome, greater abundance of pro-inflammatory species such as *Escherichia coli* (

39.

Rhodes, J.M.

**The role of Escherichia coli in inflammatory bowel disease**

*Gut.* 2007; **56**:610-612

) and *Ruminococcus gnavus* (

26.

Hall, A.B. ∙ Yassour, M. ∙ Sauk, J....

**A novel Ruminococcus gnavus clade enriched in inflammatory bowel disease patients**

*Genome Med.* 2017; **9**:103

), and depletion of species with protective mechanisms, such as short-chain fatty acid production, is associated with intestinal inflammation in IBD. In prior work (

4.

Ananthakrishnan, A.N. ∙ Luo, C. ∙ Yajnik, V....

**Gut microbiome function predicts response to anti-integrin biologic therapy in inflammatory bowel diseases**

*Cell Host Microbe.* 2017; **21**:603-610.e3

), we demonstrated that a machine-learning algorithm incorporating functional and taxonomic microbial data from stool performed accurately in predicting initial response to vedolizumab therapy. However, this prior study did not incorporate metabolomic profiling, which provides a window into the functional impact of the gut microbiome, and was limited in its duration of follow-up to examine clinical and endoscopic outcomes at 1 year after treatment. Similarly, others have demonstrated that the baseline fecal microbiome may predict response to anti-TNF or anti-IL12/23 therapy individually (

1.

Aden, K. ∙ Rehman, A. ∙ Waschina, S....

**Metabolic functions of gut microbes associate with efficacy of tumor necrosis factor antagonists in patients with inflammatory bowel diseases**

*Gastroenterology.* 2019; **157**:1279-1292.e11

;

4.

Ananthakrishnan, A.N. ∙ Luo, C. ∙ Yajnik, V....

**Gut microbiome function predicts response to anti-integrin biologic therapy in inflammatory bowel diseases**

*Cell Host Microbe.* 2017; **21**:603-610.e3

; ). However, all these studies were limited by small numbers of included patients and examination primarily of short-term improvement with one therapeutic class, precluding definition of whether microbial profiles differentially predict response based on the therapeutic mechanism of action. Here, we profile the gut metagenome of patients with moderate-to-severe CD or UC initiating anti-TNF or anti-IL12/23 (together termed anti-cytokine), or anti-integrin therapy to define microbial features that predict response to one or more therapeutic classes. By pairing metagenomic sequencing with serum proteomic and metabolomic profiles, we define the potential functional mechanisms of the impact of the microbiome on the outcome.

## Results

To study the microbial determinants of clinical outcomes, we identified eligible IBD patients initiating biologic therapy enrolled in the Prospective Registry in IBD Study at Massachusetts General Hospital (MGH) (PRISM) (

20.

Franzosa, E.A. ∙ Sirota-Madi, A. ∙ Avila-Pacheco, J....

**Gut microbiome structure and metabolic activity in inflammatory bowel disease**

*Nat. Microbiol.* 2019; **4**:293-305

). The study cohort (n = 185; 108 CD, 77 UC) consisted of 79 (42.7%) patients with moderate-to-severe IBD initiating anti-TNF, 21 (11.4%) initiating ustekinumab (anti-IL12/23) and 85 (45.9%) initiating vedolizumab (anti-integrin) therapy ([Figure 1](#fig1); [Table S1](#mmc1)). Anti-TNF and anti-IL12/23 were grouped together as anti-cytokine therapy. Stool and blood samples were collected at baseline, and each stool sample was subjected to metagenomic sequencing followed by profiling of the microbial community taxonomic composition and functional potential. Blood samples were analyzed for untargeted metabolomics and serum proteomics, to capture metabolomic and immune signaling profiles associated with putative-microbial features associated with response to different therapies. By the end of 1 year of follow-up, 91 (49.2%) achieved clinical remission status by 14 weeks and an additional 22 (11.9%) patients achieved remission at 52 weeks ([Table S2](#mmc1)). Among the 86 patients who underwent colonoscopy at 1 year, 41 (47.7%) achieved endoscopic remission.

![](https://www.cell.com/cms/10.1016/j.chom.2021.06.019/asset/212364e6-7813-45aa-801e-4c753d90e969/main.assets/gr1_lrg.jpg)

Figure 1 Study overview

### Baseline microbial metacommunity differentially predicts response to anti-cytokine therapy

Consistent with prior smaller studies, patients treated with anti-cytokine therapy who achieved clinical remission at 14 weeks (p < 0.1) and at 1 year (p < 0.01) had significantly higher indices of microbial species richness at baseline ([Figures S1](#mmc1) A–S1C), and likewise for Shannon diversity, although the latter was not statistically significant. The indices of alpha diversity (both richness and Shannon) positively correlated (p < 0.05) with a diagnosis of UC, concomitant use of steroids, immunomodulators, and prior TNF exposure, and were negatively correlated with concomitant use of antibiotics ([Figures S1](#mmc1) D and S1E).

Using Dirichlet multinomial mixture (DMM) models to partition microbial community profiles into a finite number of clusters using Laplace approximation, we identified two distinct metacommunities, designated “DMM group 1” and “DMM group 2” ([Figure 2](#fig2) A). The optimal number of clusters determined was congruent with results from a partitioning around medoid (PAM)-based clustering approach (see [Figure S1](#mmc1) F). Metacommunity DMM group 1 was represented predominantly by microbial species of the Firmicutes phyla including *Faecalibacterium prausnitzii* and *Ruminococcus bromii*. DMM group 1 also had a more diverse community profile ([Figure 2](#fig2) B). In contrast, DMM group 2 was represented by *Bacteroides ovatus*, *B. thetaiotaomicron*, and *Veillonella parvula,* among others ([Figure 2](#fig2) C). Baseline community membership was an important determinant of clinical outcomes depending on the therapeutic mechanism of action ([Figure 2](#fig2) D). Patients on anti-cytokine therapy who subsequently achieved clinical remission at 14 weeks, at 1 year, and endoscopic remission at 1 year had higher baseline microbial richness. For patients initiating anti-cytokine therapy, the rates of clinical remission at week 14 (73.3% versus 41.2%, p = 0.02), week 52 (66.7% versus 36.4%, p < 0.01), and endoscopic remission (65% versus 37.5%, p = 0.09) were much higher in those belonging to the DMM group 1 at baseline when compared with group 2.

![](https://www.cell.com/cms/10.1016/j.chom.2021.06.019/asset/1f338f41-9c21-48e0-be57-7d927e07e37c/main.assets/gr2_lrg.jpg)

Figure 2 Fecal metagenomics predicts differential response to anti-cytokine and anti-integrin therapy

The microbiome profiles among IBD patients may differ significantly, depending on IBD subtype (i.e., CD and UC) and initial disease severity (

33.

Lloyd-Price, J. ∙ Arze, C. ∙ Ananthakrishnan, A.N....

**Multi-omics of the gut microbial ecosystem in inflammatory bowel diseases**

*Nature.* 2019; **569**:655-662

;

42.

Schirmer, M. ∙ Denson, L. ∙ Vlamakis, H....

**Compositional and temporal changes in the gut microbiome of pediatric ulcerative colitis patients are linked to disease course**

*Cell Host Microbe.* 2018; **24**:600-610.e4

). We thereby performed additional sub-analyses by further sub-stratifying the proportion of week 14 responders to either anti-cytokine therapy or vedolizumab therapy according to subtype of IBD or baseline disease severity and their corresponding baseline metagenomic DMM group. We also used a cutoff of 8 with the Harvey Bradshaw index for patients with CD, and cutoff of 5 with the simple clinical colitis activity index for patients with UC, to define moderate-severe IBD activity (

36.

Peyrin-Biroulet, L. ∙ Panés, J. ∙ Sandborn, W.J....

**Defining disease severity in inflammatory bowel diseases: current and future directions**

*Clin. Gastroenterol. Hepatol.* 2016; **14**:348-354.e17

) in order to investigate preferential response to either anti-cytokine or anti-integrin therapy. Of note, the preferential response to anti-cytokine therapy to anti-integrin therapy among patients with baseline DMM group 1 metacommunities is independent of the IBD subtype (CD; 77.3% versus 45.4%, UC; 57.1% versus 39.3%, [Figure S1](#mmc1) G) or baseline disease severity (mild; 83.3% versus 62.5%, moderate-severe; 64.7% versus 41.7%, [Figure S1](#mmc1) H).

### Taxonomic and functional-metagenomic features associated with remission

To test association with clinical outcomes after exposure to either therapeutic class, while controlling for other covariates (such as age, subtype of IBD, duration of disease, and medication use), we applied a multivariable linear model to each microbial taxonomic feature present in at least 10 samples with 0.1% relative abundance. The abundances of nine microbial species at baseline (qval < 0.2) were linked to early clinical remission among patients treated with anti-cytokine and three microbial species for anti-integrin therapy ([Figure 2](#fig2) E; [Table S3](#mmc2)). Several of these species, including *Phascolarctobacteriaum faecium*, *Agathobaculum butyriciproducens*, and *Clostridium citroneae* have previously demonstrated anti-inflammatory effects, primarily through altering the fecal short-chain fatty acid production (

47.

Watanabe, Y. ∙ Nagai, F. ∙ Morotomi, M.

**Characterization of Phascolarctobacterium succinatutens sp. nov., an asaccharolytic, succinate-Utilizing Bacterium Isolated from Human Feces**

*Appl. Environ. Microbiol.* 2012; **78**:511-518

). Interestingly, certain species specifically associated with remission either for anti-cytokine therapy (example C. *citronae, A. butyriciproducens*) or anti-integrin alone (*B. stercoris*), whereas others demonstrated similar effects for both therapeutic mechanisms (*B. caccae* and *B. ovatus*). Overall, the association between baseline microbiome and remission was stronger for week 14 outcomes for both therapeutic mechanisms than with week 52 clinical or endoscopic remission, suggesting that the clinical impact of the microbiome is strongest on more proximate events.

To understand the functional consequences of microbial composition changes leading to remission, we profiled the gene families in all metagenomes using HUMAnN3 and then summed their abundances according to the Enzyme Commission (EC) number annotations. We then applied the linear modeling approach described earlier to enzyme abundance data, revealing 120 enzymes, from six enzyme classes, which were mostly differentially abundant (qval < 0.2) in baseline samples from patients receiving anti-cytokine who achieved early remission compared with non-remitters ([Table S3](#mmc2)). When examining species-level functional-attribution data, 6.8% (8/120) of the enzymes were explained by a single species contributing >50% of the enzyme copies in >50% of the samples (hereafter single-species dominance). *Eggerthella lenta* alone dominated 5 of the 8 enzymes, 3 of which (EC 1.1.1.391, EC 3.1.2.26, EC 1.1.1.52) are associated with secondary bile acid biosynthesis. The remaining 112 enzymes that were not associated with single-species dominance were mostly enriched in non-remitter subjects, compared with those having early remission. Two-fifths of these enzymes (28/70) belonged to class EC3 (hydrolase activity; mainly EC 3.2, acting on glycosyl bonds) ([Figure S2](#mmc1)). Glycoside hydrolases are involved in the breakdown and utilization of mucin-derived glycans and the loss of particular glycans, such as complex O-glycans, can result in spontaneous colitis (

21.

Fu, J. ∙ Wei, B. ∙ Wen, T....

**Loss of intestinal core 1-derived O-glycans causes spontaneous colitis in mice**

*J. Clin. Invest.* 2011; **121**:1657-1666

).

### Serum secondary bile acids predict clinical remission

We conducted metabolome analysis on baseline blood samples from patients undergoing anti-cytokine therapy, using four liquid chromatography tandem mass spectrometry (LC-MS) methods previously described (

20.

Franzosa, E.A. ∙ Sirota-Madi, A. ∙ Avila-Pacheco, J....

**Gut microbiome structure and metabolic activity in inflammatory bowel disease**

*Nat. Microbiol.* 2019; **4**:293-305

). A total of 541 unique features were matched against reference data generated from an in-house compound library and binned into metabolite classes as defined by the Human Metabolome Database (HMDB) ([Figure S3](#mmc1) A). Using the same multivariable linear regression model described earlier, a total of 27 putative metabolomic biomarkers associated with clinical outcomes (pval < 0.05; qval < 0.2) were identified. Eleven of these were associated with week 14 remission, and the remaining sixteen were associated with non-remission. Ten of the eleven metabolomic features associated with early remission were categorized as either carboxylic acids (n = 4), steroid derivatives (n = 4), and tetrapyrroles (n = 2), whereas the majority of metabolomic features associated with non-remission (9/16) were either glycerolipids or glycerophospholipids ([Figure 3](#fig3) A).

![](https://www.cell.com/cms/10.1016/j.chom.2021.06.019/asset/af77bf79-6f37-496d-ae81-140f261dc0da/main.assets/gr3_lrg.jpg)

Figure 3 Serum secondary bile acids predict early remission with anti-cytokine therapy

We performed enrichment analysis, including all 63 differential metabolite features with nominal p value < 0.1 ([Table S3](#mmc2)), to profile broad classes of compounds that were significantly overabundant in patients who achieved week 14 remission compared with non-remitters ([Figure 3](#fig3) B). Patients who did not achieve week 14 remission had significant enrichment of serum glycerophosphoethanolamines (q < 0.01) and diacylglycerols (q = 0.03). Patients with week 14 remission had significant enrichment of serum bile acids (enrichment ratio 1.85, q < 0.01), specifically secondary bile acids, such as glycolithocholate (log <sub>2</sub> -fold difference: 1.66, p = 0.04), glycodeoxycholate (log <sub>2</sub> -fold difference: 1.35, p = 0.04), and ursodeoxycholate (log <sub>2</sub> -fold difference: 1.21, p = 0.03) in baseline serum samples ([Figure 3](#fig3) C).

### The gut metagenome may be a source of secondary bile acid production influencing clinical outcomes

The conversion from primary to secondary bile acids is a function restricted to a narrow range of clostridial species and mediated by 7α/β-dehydroxylation enzymes (

22.

Funabashi, M. ∙ Grove, T.L. ∙ Wang, M....

**A metabolic pathway for bile acid dehydroxylation by the gut microbiome**

*Nature.* 2020; **582**:566-570

), of which BaiB, BaiCD, BaiA2, BaiE, BaiF, and BaiH were previously shown to be sufficient with no additional enzymes required. Although we have already revealed a few microbial EC features contributing to secondary bile acid biosynthesis that are significantly overabundant among patients who achieve week 14 remission on anti-cytokine therapy, we investigated the role of the gut microbiome in determining bile acid metabolite concentrations in greater detail. We mapped the gut metagenome of patients against the recently published *de novo* assembled gene catalog, (

30.

Kenny, D.J. ∙ Plichta, D.R. ∙ Shungin, D....

**Cholesterol metabolism by uncultured human gut bacteria influences host cholesterol level**

*Cell Host Microbe.* 2020; **28**:245-257.e6

) which grouped clusters of homologous proteins to uncover homologs of the 8 enzymes making up the *bai* operon, which is responsible for bile acid 7α/β-dehydroxylation (

22.

Funabashi, M. ∙ Grove, T.L. ∙ Wang, M....

**A metabolic pathway for bile acid dehydroxylation by the gut microbiome**

*Nature.* 2020; **582**:566-570

). Among patients with paired serum and stool samples at baseline, we found significant correlations (R > 0.5, pval < 0.01) between the abundance of the *bai* operon enzymes and the relative intensities of secondary bile acids glycolithocholate and glycodeoxycholate ([Figure 3](#fig3) D). We subsequently classified individual gut metagenomic samples as either bile acid 7α/β-dehydroxylation capable (*bai+*) or incapable (*bai−*) ([Figure 3](#fig3) E), determined by the presence or absence of the set of *bai* operon enzymes described earlier, and found that a larger fraction of patients with baseline metacommunity DMM group 1, which favored response to anti-cytokine therapy, were classified as *bai* -operon-positive (*bai+*) compared with patients with baseline DMM group 2 (79.1% versus 32.6%; p < 0.01) ([Figure 3](#fig3) E). Among *bai+* patients (60.2% of the cohort), patients undertaking anti-cytokine therapy were more likely to achieve week 14 remission compared with patients taking anti-integrin therapy (OR 3.52, 95% CI: 1.30–10.1, p = 0.02).

### Validation of metagenomic and metabolomic associations

To validate the metagenomic associations mentioned earlier with anti-cytokine response, we obtained baseline metagenomic profiles of 46 patients undergoing infliximab therapy from two prior published studies (

32.

Lewis, J.D. ∙ Chen, E.Z. ∙ Baldassano, R.N....

**Inflammation, antibiotics, and diet as environmental stressors of the gut microbiome in pediatric Crohn’s disease**

*Cell Host Microbe.* 2015; **18**:489-500

;

33.

Lloyd-Price, J. ∙ Arze, C. ∙ Ananthakrishnan, A.N....

**Multi-omics of the gut microbial ecosystem in inflammatory bowel diseases**

*Nature.* 2019; **569**:655-662

). In the validation cohort, 6 of the 9 species associated with anti-cytokine response in our prospective cohort met the abundance threshold (i.e., present in at least 10% of samples with 0.1% relative abundance) for further analysis. Using a 5-fold cross-validation random forest classifier on the prospective cohort dataset, the supervised machine-learning model performed reasonably well in predicting therapy response in the validation cohort (Accuracy 0.74, 95% CI: 0.59–0.86), whereby a majority of these taxonomic features associated with anti-cytokine response in the prospective PRISM cohort (n = 4/6; *Eggerthella lenta*, *Collinsella stercoris*, *Gordonibacter pamelaeae*, *Bacteroides ovatus*) were among the top 20 features by importance ([Figure S4](#mmc1) A). We also replicated the association with *bai+* operon positivity and preferential anti-cytokine therapy response. As in the primary cohort, in the independent validation cohort we found a high proportion of responders to anti-cytokine therapy (76.5%, [Figure 3](#fig3) F) among patients who were baseline *bai+*, and this was associated with a 5-fold higher likelihood of clinical remission at week 14 among patients on anti-cytokine therapy in the validation cohort when compared with vedolizumab users in the original manuscript (OR 5.42, 95% CI: 1.59–22.1, p = 0.01).

Secondary bile acids have been hypothesized to have an anti-inflammatory role in the gut, whereby administration of lithocholic acid was able to ameliorate disease in murine model of colitis (

44.

Sinha, S.R. ∙ Haileselassie, Y. ∙ Nguyen, L.P....

**Dysbiosis-induced secondary bile acid deficiency promotes intestinal inflammation**

*Cell Host Microbe.* 2020; **27**:659-670.e5

). To support mechanistic plausibility of the association between presence of the *bai* operon and response to biologic therapy, we examined the association between *bai+* status, fecal secondary bile acid concentrations, and fecal calprotectin measurements using paired fecal metagenomics and metabolomics from 220 participants from previously published studies (

20.

Franzosa, E.A. ∙ Sirota-Madi, A. ∙ Avila-Pacheco, J....

**Gut microbiome structure and metabolic activity in inflammatory bowel disease**

*Nat. Microbiol.* 2019; **4**:293-305

). We then found that patients with *bai+* status have a correspondingly higher abundance of fecal secondary bile acids (deoxycholic acid, tauro-lithocholic acid, and tauro-ursodeoxycholic acid; p < 0.05, [Figure S4](#mmc1) B). We further demonstrated that patients with active disease (i.e., elevated fecal calprotectin) have lower fecal deoxycholic acid measurements (p < 0.05, [Figure S4](#mmc1) C), whereby fecal calprotectin is an established surrogate marker of gut inflammation (

40.

Rubin, D.T. ∙ Ananthakrishnan, A.N. ∙ Siegel, C.A....

**Clinical Guideline: Ulcerative Colitis in Adults**

*Am J Gastroenterol.* 2019 Mar; **114** (3):384-413

). These findings support the potential mechanistic role of secondary bile acid concentrations in attenuating luminal inflammation and enhancing biologic therapy response.

### Serum cytokines correlated to microbial diversity are associated with remission

To expand our biomarker discovery effort, we profiled 104 unique serum protein biomarkers which were selected *a priori* based on their direct or indirect role in inflammation and the immune response. These protein markers represent a wide range of gene ontology (GO) immune-related biological functions, such as cytokine-mediated signaling (GO0019221), chemokine-mediated signaling (GO0070098), and cellular response to TNF (GO0033209) ([Figure S3](#mmc1) B). Using the same multivariate linear model described earlier for metagenomics and metabolomics, a total of 9 serum proteins were significantly associated with remission outcome in at least one patient group ([Figure 4](#fig4) A) after correcting for other covariates (age, subtype of IBD, duration of disease, and medication use). The majority (6/9) of the putative serum proteins were associated with endoscopic remission rather than clinical remission at either week 14 or at 1 year. Likewise, most putative proteins were only significantly associated for either patients treated with anti-cytokine (i.e., CD6, CD244, TRAIL, IL18, ADA) or anti-integrin therapy (i.e., NT3, IFNLR1, PIK3AP1). Only CASP8 was significantly associated for both classes of therapeutics, whereby it was positively associated with endoscopic remission for patients taking anti-cytokine therapy (pval = 0.02) and inversely associated with clinical remission with anti-integrin therapy (pval < 0.001, qval = 0.16). Baseline serum TNF, IL-12, IL-22, and IL-23 were not predictive of week 14 or week 52 remission with either therapeutic class.

![](https://www.cell.com/cms/10.1016/j.chom.2021.06.019/asset/a793daa0-c7e6-4275-97db-a5d45ef33f83/main.assets/gr4_lrg.jpg)

Figure 4 Serum protein markers associated with microbial diversity and clinical remission

As the microbiome, and metagenomic diversity in particular, was an indicator of anti-cytokine response, we investigated the association of serum immune proteins with prevalent metagenomic taxonomic features, as well as metagenomic indices of alpha diversity. A total of 27 unique proteins were associated with at least one microbial feature at FDR 0.1 ([Table S3](#mmc2)). Most of these proteins (25/27) were significantly associated with at least one metagenomic taxonomic feature ([Figure 4](#fig4) B; [Table S3](#mmc2)). Although most of the microbial associations to proteins were previously unknown several have previously been linked to either inflammation or immune response in IBD. Enrichment of *Alistipes* in *NOD2* knockout mice was associated with anti-inflammatory cytokines (TGF-B, IL10) and attenuated 2,4,6-Trinitrobenzene sulfonic acid-induced colitis (

10.

Butera, A. ∙ Di Paola, M. ∙ Pavarini, L....

**Nod2 deficiency in mice is associated with microbiota variation favouring the expansion of mucosal CD4+ LAP+ regulatory cells**

*Sci. Rep.* 2018; **8**:14241

). Four proteins were associated with indices of metagenomic alpha diversity ([Figure 4](#fig4) C). FGF19 (R = 0.44, q < 0.05) and ZBTB16 (R = 0.40, q = 0.09) were positively correlated with microbial richness, whereas IL10RB (R = −0.42, q = 0.08) and IL12RB1 (R = −0.39, q = 0.08) were both inversely correlated with Shannon alpha diversity. All 4 of the proteins associated with metagenomic diversity were also differentially expressed between patients with either baseline metacommunities ([Figure 4](#fig4) D), whereby patients with baseline metacommunity 1 had increased mean serum expression of FGF19 (log <sub>2</sub> -fold difference: 0.97, p = 0.01) and ZBTB16 (log <sub>2</sub> -fold difference: 0.65, p = 0.001) and patients with baseline metacommunity 2 had increased mean serum expressions of IL10RB (log <sub>2</sub> -fold difference: 0.20, p = 0.03) and IL12RB1 (log <sub>2</sub> -fold difference: 0.26, p = 0.03).

### Multi-omics to predict treatment response

Previously we demonstrated among patients taking vedolizumab that baseline clinical features alone were insufficient in predicting remission at week 14 (AUC 0.619), and the use of microbial taxa (AUC 0.715) and pathways (AUC 0.738) resulted in improved predictive ability (

4.

Ananthakrishnan, A.N. ∙ Luo, C. ∙ Yajnik, V....

**Gut microbiome function predicts response to anti-integrin biologic therapy in inflammatory bowel diseases**

*Cell Host Microbe.* 2017; **21**:603-610.e3

). Here, we aim to highlight the incremental value of each layer of information among patients taking anti-cytokine therapy using random forest classifiers with feature selection and leave-one-out cross-validation; a model using only baseline clinical features performed poorly in predicting week 14 remission with an AUC of 0.624. In contrast, adding metagenomic, metabolomic, or proteomic features significantly increased the predictive value with AUCs of 0.849, 0.773, and 0.806, respectively ([Figure 4](#fig4) E). Among the 21 participants with available proteomic, metabolomic, and metagenomic profiles at baseline, the AUC of the clinical + metagenomic + metabolomic + proteomic markers in predicting response was 96.3% (95% CI 0.88–1). Furthermore, all three 'omic profiles were only available in those initiated on anti-cytokine therapy. Although the integrative analysis was undertaken with internal cross-validation, more robust examinations in larger cohorts are essential prior to application to clinical practice.

## Discussion

With availability of multiple therapeutic mechanisms of action, identifying determinants of overall likelihood to improve with treatment, as well as of the more nuanced response to a given treatment class, is of high priority in the management of IBD. Here, by applying high throughput 'omic profiling to a prospective cohort of patients initiating anti-cytokine or anti-integrin therapy for the management of moderate-to-severe IBD, we identify unique microbial signatures that may preferentially favor response to a specific therapeutic class. We also propose mechanisms for the beneficial effects of a favorable microbial profile.

An important finding from our analysis was the association of microbial metacommunities with distinct likelihoods of response to either anti-integrin or anti-cytokine therapy. The specificity of this association suggests the existence of unique biologic mechanisms that determine response to an individual therapy class, despite broadly similar therapeutic efficacy of antibodies targeting either mechanism. Many of the bacterial species associated with remission after anti-cytokine therapy have well-described anti-inflammatory effects, often by contributing to a favorable fecal short-chain fatty acid profile. Patients more likely to achieve remission with anti-cytokine therapy had a greater abundance of colonic butyrate-producing microbial species, which promotes intestinal homeostasis (i.e., *Agathobaculum butyricproduces*, *Clostridium citroneae*). They also had increased abundance of succinate-consuming microbial species, such as *Phascolarctobacteriaum faecium* (

47.

Watanabe, Y. ∙ Nagai, F. ∙ Morotomi, M.

**Characterization of Phascolarctobacterium succinatutens sp. nov., an asaccharolytic, succinate-Utilizing Bacterium Isolated from Human Feces**

*Appl. Environ. Microbiol.* 2012; **78**:511-518

). Accumulation of luminal succinate, which is primarily microbial in origin, can lead to intestinal inflammation. Binding of succinate to the SUCNR1, a G-protein-coupled receptor widely expressed across intestinal and immune cells, can act in an autocrine and paracrine manner to increase inflammatory responses in myeloid cells, enhance production of IL-1β, and act as a chemotactic factor for dendritic cells, resulting in antigen-specific T cell activation (

13.

Connors, J. ∙ Dawe, N. ∙ Van Limbergen, J.

**The role of succinate in the regulation of intestinal inflammation**

*Nutrients.* 2018; **11**:25

;

34.

Macias-Ceja, D.C. ∙ Ortiz-Masiá, D. ∙ Salvador, P....

**Succinate receptor mediates intestinal inflammation and fibrosis**

*Mucosal Immunol.* 2019; **12**:178-187

). Among patients initiating anti-integrin therapy, on the other hand, remitters had increased abundances of *Bifidobacterium longum* and *Bacteroides species* (*B. ovatus*, *B. stercoris*). Some of the bacterial species that associated with clinical remission have also demonstrated efficacy as standalone microbiome-directed therapy. In a murine colitis model, *B. ovatus* monotherapy was superior to fecal transplantation in achieving clinical remission after DSS administration to C57BL/6 mice (

28.

Ihekweazu, F.D. ∙ Fofanova, T.Y. ∙ Queliza, K....

**Bacteroides ovatus ATCC 8483 monotherapy is superior to traditional fecal transplant and multi-strain bacteriotherapy in a murine colitis model**

*Gut Microbes.* 2019; **10**:504-520

). In a study of patients with CD, gain of *B. longum* was associated with maintenance of remission (

31.

Kong, L. ∙ Lloyd-Price, J. ∙ Vatanen, T....

**Linking strain engraftment in fecal microbiota transplantation with maintenance of remission in Crohn’s disease**

*Gastroenterology.* 2020; **159**:2193-2202.e5

). Interestingly, the association between the microbiome and clinical response was stronger for week 14 remission than week 52 clinical or endoscopic outcomes. This suggests that the influence of the microbiome may be more dominant on proximate outcomes. A systematic study of different time intervals between microbial profiling and clinical features is important to better identify the optimal predictive window for the microbiome for individual clinical outcomes.

Direct comparison of the metagenomic profiles contributing to our metacommunity definitions with other landmark studies using enterotyping are limited by heterogeneity in the patient population and intent of partitioning into subgroups.

29.

Jacobs, J.P. ∙ Goudarzi, M. ∙ Singh, N....

**A disease-associated microbial and Metabolomics State in relatives of pediatric inflammatory bowel disease patients**

*Cell. Mol. Gastroenterol. Hepatol.* 2016; **2**:750-766

used 16S rRNA profiling of populations that contained a mix of patients with IBD and healthy controls to define enterotypes that predicted IBD diagnosis in the study population, or a predisposition toward developing IBD in healthy first-degree relatives.

14.

Costea, P.I. ∙ Hildebrand, F. ∙ Arumugam, M....

**Enterotypes in the landscape of gut microbial community composition**

*Nat. Microbiol.* 2018; **3**:8-16

and

48.

Wu, G.D. ∙ Chen, J. ∙ Hoffmann, C....

**Linking long-term dietary patterns with gut microbial enterotypes**

*Science.* 2011; **334**:105-108

also used 16S rRNA profiling in healthy individuals to define enterotypes and microbial species favoring a specific enterotype. However, neither of the two latter studies included patients with IBD. To our knowledge, there are no prior studies using metagenomic data to partition patients with moderate-to-severe IBD into distinct microbial communities with implications for clinical phenotype, such as therapy response. The metagenomic profile in our cohort reveals both the effect of chronic inflammation on the microbiome in comparison with the microbial features informing enterotype definition described in prior studies (

5.

Arumugam, M. ∙ Raes, J. ∙ Pelletier, E....

**Enterotypes of the human gut microbiome**

*Nature.* 2011; **473**:174-180

) and also species-level differences within a genus that highlights the importance of metagenomic sequencing studies.

Serum metabolomic profiling also yielded insight into a patient's potential response to treatment. We observed a strong association between serum secondary bile acid concentrations and likelihood of achieving remission with anti-cytokine therapy. Secondary bile acid-induced stimulation of the FXR is protective in chemically induced colitis models (

44.

Sinha, S.R. ∙ Haileselassie, Y. ∙ Nguyen, L.P....

**Dysbiosis-induced secondary bile acid deficiency promotes intestinal inflammation**

*Cell Host Microbe.* 2020; **27**:659-670.e5

). We also demonstrated that modification of secondary bile acid profiles may be a mechanism by which the gut microbial composition determines response to biologic therapy. This may occur via a group of Bai 7α/β-dehydroxylation enzymes. Microbial metacommunities with increased abundance of Bai 7α/β-dehydroxylation component microbial microorganisms are more likely to be found in patients responsive to anti-cytokine therapy. This may explain why increased diversity (and therefore more microbes contributing these enzymes) also associates with a positive response. An association between microbial diversity and treatment response is consistent with other observations that diversity is associated with superior rates of remission. Microbial diversity was also inversely associated with serum cytokine profiles (i.e., IL10RB, IL12RB1) that favored resistance rather than response to anti-cytokine therapy.

Similarly, serum proteins associated with remission for either patients treated with anti-cytokine (i.e., CD6, CD244, TRAIL, IL18, ADA, caspase-8) or anti-integrin therapy (i.e., NT3, IFNLR1, PIK3AP1) tended to be specific to each individual class. The anti-inflammatory roles of some of these cytokines are well established. For example, TRAIL, a transmembrane protein belonging to the TNF superfamily, suppresses gut inflammation and inhibits colitogenic T cell activation via apoptosis-independent pathways (

12.

Chyuan, I.T. ∙ Tsai, H.F. ∙ Wu, C.S....

**TRAIL suppresses gut inflammation and inhibits colitogeic T-cell activation in experimental colitis via an apoptosis-independent pathway**

*Mucosal Immunol.* 2019; **12**:980-989

). The association between caspase-8 and response to anti-cytokine therapy highlights specific TNF-mediated pathways mediating remission among patients on anti-cytokine therapy. Caspase-8 regulates intestinal homeostasis, protecting intestinal epithelial cells from TNF-α-induced necroptotic cell death (

25.

Günther, C. ∙ Martini, E. ∙ Wittkopf, N....

**Caspase-8 regulates TNF-α-induced epithelial necroptosis and terminal ileitis**

*Nature.* 2011; **477**:335-339

). In contrast, the association between IFNLR1 and response to anti-integrin therapy suggests a more dominant role for neutrophil migration in mediating inflammation in these patients. IFNLR1, is usually expressed by neutrophils within the mucosal lamina propria to mediate the anti-inflammatory effects of IFNɣ. IFNLR1 knockout mice demonstrated more severe intestinal inflammation than wild-type mice when exposed to DSS, exemplifying its anti-inflammatory activity (

9.

Broggi, A. ∙ Tan, Y. ∙ Granucci, F....

**IFN-λ suppresses intestinal inflammation by non-translational regulation of neutrophil function**

*Nat. Immunol.* 2017; **18**:1084-1093

). Some of the associations identified, such as IL18, which has been shown here to be positively associated with mucosal healing, are different from the observed literature and require the need for wider replication studies.

One limitation of our study was that remission relied primarily on clinical indicators with fewer than half of the cohort having endoscopic outcomes available. Furthermore, not all patients provided both stool and serum at baseline, limiting our statistical power. Despite the study limitations, there are several important implications to our findings. First, we demonstrate that microbial signals that mediate response to immunosuppressive treatment vary by therapeutic class. Harnessing this variability through precision-medicine approaches would allow for tailored therapy at the individual patient level to ensure early response and prevent protracted morbidity due to sequential empiric treatment trials. Our study findings highlight a role not just for microbial taxonomy, but for microbially encoded pathways that may be relevant to treatment. These pathways have been validated by changes in abundance of serum metabolites and corresponding cytokine readouts. Specifically, our study highlights an important role of the microbiome in determining luminal short-chain fatty acid and succinate concentrations that may determine the course of inflammation. Our findings also demonstrate a role for bile acid metabolism, particularly secondary bile acids, as a determinant of response to anti-cytokine therapy in IBD. Identification of predictive microbial signals could also allow for refinement of novel probiotics that may deliver specific anti-inflammatory functions or stimulate anti-inflammatory metabolic pathways that may act in ameliorating gut inflammation. The omics profiles identified in this study could serve as targets for newer therapies and shed further light on the pathogenesis and progression of these complex diseases.

## STAR★Methods

### Key resources table

<table><thead><tr><th>REAGENT or RESOURCE</th><th>SOURCE</th><th>IDENTIFIER</th></tr></thead><tbody><tr><td colspan="3"><b>Biological Samples</b></td></tr><tr><td>IBD patients fecal and serum samples</td><td>Crohn’s and Colitis Center, Massachusetts General Hospital and Harvard Medical School</td><td>PRISM</td></tr><tr><td colspan="3"><b>Critical Commercial Assays</b></td></tr><tr><td>Mini Bead beater-8</td><td>Biospec Products</td><td>Cat# 693</td></tr><tr><td>QIAshredder</td><td>Qiagen</td><td>Cat# 79654</td></tr><tr><td>Proteinase K</td><td>Qiagen</td><td>Cat# 19131</td></tr><tr><td>AllPrep DNA/RNA Mini Kit</td><td>Qiagen</td><td>Cat# 80204</td></tr><tr><td>Nextera XT DNA Library Preparation kit</td><td>Illumina</td><td>Cat# FC-131-1096</td></tr><tr><td colspan="3"><b>Deposited Data</b></td></tr><tr><td>Shotgun metagenomic sequences</td><td>Sequence Read Archive</td><td>PRJNA685168</td></tr><tr><td colspan="3"><b>Software and Algorithms</b></td></tr><tr><td>bioBakery meta’omics workflow</td><td>(<p>35.</p><p>McIver, L.J. ∙ Abu-Ali, G. ∙ Franzosa, E.A....</p><p><strong>bioBakery: a meta’omic analysis environment</strong></p><p><em>Bioinformatics.</em> 2018; <strong>34</strong>:1235-1237</p>)</td><td><a href="https://app.terra.bio/#workspaces/rjxmicrobiome/mtx_workflow">https://app.terra.bio/#workspaces/rjxmicrobiome/mtx_workflow</a></td></tr><tr><td>Trimmomatic (v0.36)</td><td>(<p>8.</p><p>Bolger, A.M. ∙ Lohse, M. ∙ Usadel, B.</p><p><strong>Trimmomatic: a flexible trimmer for Illumina sequence data</strong></p><p><em>Bioinformatics.</em> 2014; <strong>30</strong>:2114-2120</p>)</td><td><a href="http://www.usadellab.org/cms/?page=trimmomatic">http://www.usadellab.org/cms/?page=trimmomatic</a></td></tr><tr><td>KneadData (v0.7.2)</td><td>Huttenhower lab</td><td><a href="http://huttenhower.sph.harvard.edu/kneaddata">http://huttenhower.sph.harvard.edu/kneaddata</a></td></tr><tr><td>Metaphlan 3</td><td>(<p>7.</p><p>Beghini, F. ∙ McIver, L.J. ∙ Blanco-Míguez, A....</p><p><strong>Integrating taxonomic, functional, and strain-level profiling of diverse microbial communities with bioBakery 3</strong></p><p><em>eLife.</em> 2021; <strong>10</strong>:e65088</p>)</td><td><a href="https://huttenhower.sph.harvard.edu/metaphlan">https://huttenhower.sph.harvard.edu/metaphlan</a></td></tr><tr><td>HUMAnN3</td><td>(<p>19.</p><p>Franzosa, E.A. ∙ McIver, L.J. ∙ Rahnavard, G....</p><p><strong>Species-level functional profiling of metagenomes and metatranscriptomes</strong></p><p><em>Nat. Methods.</em> 2018; <strong>15</strong>:962-968</p>)</td><td><a href="https://huttenhower.sph.harvard.edu/humann">https://huttenhower.sph.harvard.edu/humann</a></td></tr><tr><td>MaAsLin2</td><td>Huttenhower lab</td><td><a href="https://huttenhower.sph.harvard.edu/maaslin/">https://huttenhower.sph.harvard.edu/maaslin/</a></td></tr><tr><td>MSPminer</td><td>(<p>37.</p><p>Plaza Oñate, F. ∙ Le Chatelier, E. ∙ Almeida, M....</p><p><strong>MSPminer: abundance-based reconstitution of microbial pan-genomes from shotgun metagenomic data</strong></p><p><em>Bioinformatics.</em> 2019; <strong>35</strong>:1544-1552</p>)</td><td><a href="https://www.enterome.com/downloads/">https://www.enterome.com/downloads/</a></td></tr><tr><td>USEARCH (v8.1)</td><td>(<p>17.</p><p>Edgar, R.C.</p><p><strong>Search and clustering orders of magnitude faster than BLAST</strong></p><p><em>Bioinformatics.</em> 2010; <strong>26</strong>:2460-2461</p>)</td><td><a href="https://www.drive5.com/usearch/">https://www.drive5.com/usearch/</a></td></tr><tr><td>Metabolanalyst 4.0</td><td>(<p>11.</p><p>Chong, J. ∙ Wishart, D.S. ∙ Xia, J.</p><p><strong>Using MetaboAnalyst 4.0 for comprehensive and integrative metabolomics data analysis</strong></p><p><em>Curr. Protoc. Bioinformatics.</em> 2019; <strong>68</strong>:e86</p>)</td><td><a href="https://www.metaboanalyst.ca/">https://www.metaboanalyst.ca/</a></td></tr><tr><td>R (v3.6.1)</td><td>packages for analytical part:<br>vegan, finalfit, tidyverse, broom, qvalue, HMP</td><td><a href="http://ttps/://www.r-project.org/">ttps://www.r-project.org/</a></td></tr></tbody></table>

- [Open table in a new tab](https://www.cell.com/action/showFullTableHTML?isHtml=true&tableId=undtbl1&pii=S1931-3128%2821%2900301-2)

### Resource availability

#### Lead contact

Further information and requests for resources and reagents should be directed to the lead contact, Ramnik J. Xavier ([xavier@molbio.mgh.harvard.edu](mailto:xavier@molbio.mgh.harvard.edu)).

#### Materials availability

Materials generated in this study are available from the the Lead Contact without restriction.

#### Data and code availability

PRISM metagenomics data is available in the Sequence Read Archive (SRA) ([https://www.ncbi.nlm.nih.gov/sra](https://www.ncbi.nlm.nih.gov/sra)): PRJNA685168.

### Experimental model and subject details

#### Study cohort

This study was nested within a longitudinal prospective IBD cohort at Massachusetts General Hospital (Prospective Registry of IBD study at MGH (PRISM). Details of this cohort have been published previously (

2.

Ananthakrishnan, A.N. ∙ Huang, H. ∙ Nguyen, D.D....

**Differential effect of genetic burden on disease phenotypes in Crohn’s disease and ulcerative colitis: analysis of a North American cohort**

*Am. J. Gastroenterol.* 2014; **109**:395-400

). In brief, the PRISM registry is open to all adult patients with IBD seeking care at the MGH Crohn’s and Colitis center. This nested study population consisted of patients with moderate-to-severe CD or UC initiating anti-TNF (infliximab, adalimumab, golimumab, certolizumab pegol), anti-IL12/23 (ustekinumab), or anti-integrin (vedolizumab) therapy. The former two therapeutic classes were grouped together as anti-cytokine therapy. Characteristics of the included patients initiating either biologic therapy are presented in [Table S1](#mmc1). Patients initiating therapy were approached for participation in the study prior to therapy initiation. Upon provision of informed consent, detailed information was obtained about disease phenotype according to the Montreal classification, current and prior treatment history including medical and surgical interventions. Concomitant medications at baseline were noted, including corticosteroids and antibiotic use. Laboratory values, including hemoglobin, serum albumin, C-reactive protein, and erythrocyte sedimentation rate, were noted. Patients with a stoma or with an ileo-anal pouch were excluded. Patients were invited to provide blood and stool samples at baseline. Blood samples were centrifuged and separated into buffy coat and serum before storage at -80°C. Stool samples were collected in 100% ethanol, aliquoted, and stored at -80°C prior to DNA extraction and metagenomic sequencing.

#### Prospective follow-up and definition of outcomes

Enrolled patients completed assessment of disease activity at baseline using validated disease activity scores utilized in clinical trials. These included the Harvey Bradshaw index (HBI) for CD (

27.

Harvey, R.F. ∙ Bradshaw, J.M.

**A simple index of Crohn’s-disease activity**

*Lancet.* 1980; **1**:514

) and simple clinical colitis activity index (SCCAI) for UC (

46.

Walmsley, R.S. ∙ Ayres, R.C. ∙ Pounder, R.E....

**A simple clinical colitis activity index**

*Gut.* 1998; **43**:29-32

). Upon prospective follow-up, patients completed these scores again at weeks 14, 30, and 54 after therapy initiation. A range of + 2 weeks was allowed around each time point for completion of these scores. Consistent with prior definitions, HBI or SCCAI scores < 2 indicated clinical remission while scores above this cut-off suggested active disease. At each follow-up visit concomitant medications were again noted as were whether IBD-related surgeries or hospitalizations had occurred in the interim.

Our primary outcome was achievement of clinical remission at week 14 with a secondary outcome being clinical remission at week 52. For patients undergoing standard of care follow-up colonoscopy to assess mucosal response, we noted whether they had achieved endoscopic remission. This was defined as Simple Endoscopic Score-CD (SES-CD) < 3 without any ulcerations for CD (

16.

Daperno, M. ∙ D’Haens, G. ∙ Van Assche, G....

**Development and validation of a new, simplified endoscopic activity score for Crohn’s disease: the SES-CD**

*Gastrointest. Endosc.* 2004; **60**:505-512

) or a Mayo endoscopic score of 0 or 1 for UC (

45.

Travis, S.P.L. ∙ Schnell, D. ∙ Krzeski, P....

**Reliability and initial validation of the ulcerative colitis endoscopic index of severity**

*Gastroenterology.* 2013; **145**:987-995

). Fecal calprotectin measurement was not widely available or reimbursed during the study period and was not systematically utilized.

#### Ethics statement

This study was approved by the Institutional Review Board of Partners Healthcare and all patients provided informed consent.

### Method details

#### Metagenomic sequencing

DNA was extracted from ~100 mg of stool using enzymatic treatment with 15 mg/ml lysozyme and proteinase K (Qiagen) for 10 min incubation followed by mechanical lysis using 0.1mm glass beads and 3 min bead beating on the “homogenize” setting of a Mini Bead beater-8 (Biospec Products). After lysis, samples were centrifuged for 5 minutes at maximum speed to pellet debris and the supernatant passed through a QIAshredder spin column (Qiagen) prior to proceeding with nucleic acid extraction using an Allprep DNA/RNA Mini Kit (Qiagen) following manufacturer protocol. Metagenomic libraries were constructed from 100–250 pg of DNA using the Nextera XT DNA Library Preparation Kit (Illumina) as per the manufacturer’s recommended protocol. Sequencing was performed on the HiSeq 2500 2x 101 PE platform (Illumina), targeting ~2.5 Gb of sequence per aliquot. Demultiplexing, BAM and FASTQ file generation were performed using the Picard suite ([https://broadinstitute.github.io/picard](https://broadinstitute.github.io/picard)).

#### Metabolomic sequencing

Serum metabolomic profiling was performed at the Broad Institute on the Broad Metabolomics platform (

20.

Franzosa, E.A. ∙ Sirota-Madi, A. ∙ Avila-Pacheco, J....

**Gut microbiome structure and metabolic activity in inflammatory bowel disease**

*Nat. Microbiol.* 2019; **4**:293-305

) Four liquid chromatography mass-spectrometry (LC-MS) methods were used to profile the following sets of metabolites. Method 1: Amino acids, acylcarnitines, dipeptides, nucleotides, and other cationic polar metabolites measured in 10 μL of serum using HILIC chromatography coupled with untargeted positive ion mode MS. Method 2: Polar and non-polar lipids, including tri-, di-, and mono-acylglycerols; phosphatidyl-cholines (PCs), -ethanolamines (PEs), and -serines; lyso-PCs and lyso-PEs; plasmalogens; cholesterol esters; ceramides; and sphingomyelins measured in 10 μL of serum using C8 chromatography and untargeted positive ion mode MS. Method 3: Short-, medium-, and long-chain free fatty acids, bile acids, and metabolites of intermediate polarity measured in 30 μL of serum using C18 chromatography and untargeted negative ion mode MS. Method 4: Central metabolites, sugars, sugar phosphates, organic acids, purines, and other anionic polar metabolites of known ID measured in 30 μL of serum using HILIC chromatography and untargeted negative ion mode MS. Known metabolites were processed using TraceFinder (v 3.0, Thermo Scientific) software by matching retention times and mass-to-charge ratio (m/z) to synthetic mixtures of reference compounds and characterized pooled plasma reference samples in each sample queue. The untargeted datasets were processed using Progenesis QI software (v 1.0, Nonlinear Dynamics). Data was standardized by relative LC-MS peak areas compared to the nearest study sample in the queue and metabolite profile data was log-transformed prior to analysis. Only 541 unique metabolites features were retained for subsequent analysis, after filtering for at least 50% presence within our cohort, and those matched with internal reference standards that were previously characterized using the Broad Institute methods.

#### Proteomic sequencing

Serum proteomic profiling was performed at Olink Proteomics (Watertown, MA) using the multiplex PEA technology (

6.

Assarsson, E. ∙ Lundberg, M. ∙ Holmquist, G....

**Homogenous 96-plex PEA immunoassay exhibiting high sensitivity, specificity, and excellent scalability**

*PLoS One.* 2014; **9**:e95192

). Two panels – inflammation and immune response – each comprising 92 biomarkers were run, testing 96 samples simultaneously in each run. The multiplex PEA technology uses paired oligonucleotide-conjugated antibodies as a probe for each protein. When the probes bind to a common target protein, the DNA oligonucleotides hybridize, allowing enzymatic DNA polymerization to produce a new DNA amplicon molecule which is quantified using a microfluidic real-time polymerase chain reaction (PCR) platform. The data for each protein was expressed as a normalized protein expression (NPX) value, which is an arbitrary unit on a log <sub>2</sub> scale allowing for normalization to minimize inter- and intra-assay variation. Only 104 unique proteomic features with at least 40% of readouts above the minimal lower limit of detection were retained for subsequent analysis.

### Quantification and statistical analysis

#### Metagenomic profiling

Metagenomic taxonomic and functional profiles were generated using the bioBakery meta’omics workflow (

35.

McIver, L.J. ∙ Abu-Ali, G. ∙ Franzosa, E.A....

**bioBakery: a meta’omic analysis environment**

*Bioinformatics.* 2018; **34**:1235-1237

) in the Terra workspace. In brief, reads mapping to the human genome were first filtered out using KneadData ([https://github.com/biobakery/kneaddata](https://github.com/biobakery/kneaddata)). Taxonomic profiles of shotgun metagenomes were generated using MetaPhlan3 (

7.

Beghini, F. ∙ McIver, L.J. ∙ Blanco-Míguez, A....

**Integrating taxonomic, functional, and strain-level profiling of diverse microbial communities with bioBakery 3**

*eLife.* 2021; **10**:e65088

), which uses a library of clade-specific markers to provide pan-microbial profiling. Functional profiling was performed by HUMAnN3 (

19.

Franzosa, E.A. ∙ McIver, L.J. ∙ Rahnavard, G....

**Species-level functional profiling of metagenomes and metatranscriptomes**

*Nat. Methods.* 2018; **15**:962-968

), whereby HUMAnN3 constructs a sample-specific reference database from the pangenomes of the subset of species detected in the samples by MetaPhlAn3 (pangenomes are precomputed represented of the open reading frames of a given species). Sample reads are mapped against this database to quantify gene presence and abundance on a per-species basis. A translated search is then performed against a UniRef-based protein sequence catalogue (UniRef release 2014\_7) for all reads that fail to map at the nucleotide level. The results are abundance profiles of gene families (UniRef90s), for both metagenomics, stratified by each species contributing to those genres, and further summarized to higher level gene groups such as ECs, KOs, or metaCYC pathways. This resulted in the generation of 506 microbial species (from 193 genera) and 2371 annotated EC features for downstream analyses. For subsequent analysis, read counts were transformed into relative abundances by normalization to the total number of reads per sample. Low-abundance filters were applied to discard taxonomic and functional features whose relative abundance did not reach 0.1% and 0.001% respectively, in at least 10% of the individuals.

#### Analysis of metagenomic diversity and metacommunities

Alpha diversity (richness and Shannon diversity) was calculated for taxonomic profiles at the species level, using the Vegan package in R. Subsequent analysis to determine the cluster of metagenomes (at the genus level) associated with remission, utilized Dirichlet multinomial (DMM) algorithms, whereby DMM bins samples on the basis of microbial community structure, and the appropriate number of clusters was determined based on the lowest Laplace approximation score. We further validated the optimal number of clusters using a partitioning around medoid (PAM)-based approach (see [Figure S3](#mmc1) F). Differential abundance analyses were performed using the LEfSe algorithm (

43.

Segata, N. ∙ Izard, J. ∙ Waldron, L....

**Metagenomic biomarker discovery and explanation**

*Genome Biol.* 2011; **12**:R60

) to identify significant species taxonomic features between DMM metacommunities with a LDA coefficient threshold of 2.5 and FDR correction threshold of 0.05. For association of metagenomic diversity and metacommunities with categorical and continuous clinical metadata, we applied Fisher’s exact tests, Mann-Whiteley *U* -tests, and logistic regression models when appropriate.

#### Differential abundance analysis of multi’omic features

We used linear models to identify putative differential abundance analysis of all omic measurement types. Features were log transformed to variance stabilize the data. Zero values were additively smoothed by half of the minimal abundance for each feature. Abundance were then log-transformed and fitted with the following per-feature linear mixed-effects model, as describe below.

feature ~ (intercept) + age + subtype of IBD + duration of disease + antibiotic use + steroids use + immunomodulator use + prior anti-TNF use + biologic class/remission status

In each per-feature multivariable model, the transformed abundance of each feature was modelled as a function of the remission status nested binary variable (with no remission sued as reference) within each biologic class (anti-cytokine, anti-integrin therapy), while adjusting for age (continuous variable), duration of disease (continuous variables), subtype of IBD (with CD as reference), and concomitant antibiotic, steroids and immunomodulator use (all binary covariates) as well as prior anti-TNF exposure (binary covariate). Fitting was performed with the MaasLin2 package in R, with nominal p-value adjusted for multiple hypothesis testing with a target FDR of 0.2.

Metabolite chemical sub-class enrichment was performed using MetaboAnalyst 4.0 (

11.

Chong, J. ∙ Wishart, D.S. ∙ Xia, J.

**Using MetaboAnalyst 4.0 for comprehensive and integrative metabolomics data analysis**

*Curr. Protoc. Bioinformatics.* 2019; **68**:e86

), with their 1072 subclass metabolite library. Enrichment ratio is computed by the ratio of observed hits over the expected hits.

#### Metagenomic profiling of Bai enzymes

To detect the presence of microbial enzymes of the *bai* operon, metagenomic sequences were mapped to the previously published gene catalogue that was assembled from geographically diverse 3097 gut metagenomes, including PRISM and HMP2 cohorts (

30.

Kenny, D.J. ∙ Plichta, D.R. ∙ Shungin, D....

**Cholesterol metabolism by uncultured human gut bacteria influences host cholesterol level**

*Cell Host Microbe.* 2020; **28**:245-257.e6

). In brief, this gene catalogue consisted of metagenomic reads from all above cohorts assembled into contigs using MegaHIT, followed by open reading frame prediction with Prodigal and a non-redundant gene catalogue was constructed by clustering predicted genes based on sequence similarity of 95% and 90% coverage of the shorter sequences using CD-HIT. Reads after mapping to the gene catalogue with BWA were filtered by at least 95% sequence identity over the read length, and normalized to transcript-per-million (TPM). USEARCH ublast was used to identify in the gene catalogue sequences homologous to genes in the bile acid inducible operon encoded by *Clostridium scindens* (

22.

Funabashi, M. ∙ Grove, T.L. ∙ Wang, M....

**A metabolic pathway for bile acid dehydroxylation by the gut microbiome**

*Nature.* 2020; **582**:566-570

) at the minimum 40% AA identity and 80% sequence coverage.

#### Correlation between multi’omic features

To study the relationship between metagenomic Bai enzymes and serum secondary bile acids profiles, we used Spearman correlation to associate the abundance of each Bai enzyme homolog TPM (log <sub>10</sub> transform) with the log <sub>2</sub> transformed serum relative intensities of glycolithocholate acid and glycodeoxycholate acid. *Bai* presence status (i.e. *bai+*) for each metagenomic sample was then coded as a dichotomous variable based on the presence (TPM > 0) of all of the following: BaiB, BaiCD, BaiA2, BaiE, BaiF and BaiH (which was previously shown to be sufficient with no additional enzymes required for 7ɑ-hydroxylation). This dichotomous variable (Bai+/Bai-) was then used for subsequent comparison of distribution between DMM metacommunities, as well as odds for remission between patients treated with either anti-cytokine therapy or anti-integrin therapy, using fisher exact and logistic regression, respectively.

To study the relationship between metagenomic features and serum proteins, we again used the Spearman correlation to associate the log-transformed metagenomic taxonomic features with NPX-normalized serum cytokines, and corrected for multiple hypothesis testing using a FDR cut off of 0.1.

#### Validation cohorts

To validate the results from our prospective cohort, we used published data from two separate studies. First, to serve as an independent validation cohort for the metagenomic associations with therapy response, we used published clinical and metagenomic data from

32.

Lewis, J.D. ∙ Chen, E.Z. ∙ Baldassano, R.N....

**Inflammation, antibiotics, and diet as environmental stressors of the gut microbiome in pediatric Crohn’s disease**

*Cell Host Microbe.* 2015; **18**:489-500

that examined outcomes after infliximab initiation in 33 children with Crohn’s disease, and data from

33.

Lloyd-Price, J. ∙ Arze, C. ∙ Ananthakrishnan, A.N....

**Multi-omics of the gut microbial ecosystem in inflammatory bowel diseases**

*Nature.* 2019; **569**:655-662

that included 13 patients with moderate-to-severe IBD initiating infliximab therapy on whom disease activity assessment using the SCCAI or HBI at 14 weeks after therapy initiation was available. Almost all of the validation cohort had Crohn’s disease (n = 45/46), with only one having ulcerative colitis. The week 14 remission rate was 65.2%, slightly higher than our prospective cohort. Raw sequences from the validation dataset were parsed through the same metagenomic pipeline outlined above, using both the reference based Metaphlan3 and the previously published *de novo* assembled gene catalogue to map for Bai enzyme homologs.

To confirm the association between secondary bile acid concentrations and reduced inflammation (higher rate of response to therapy), we used published data from two additional independent cohorts of patients with IBD, previously described by

20.

Franzosa, E.A. ∙ Sirota-Madi, A. ∙ Avila-Pacheco, J....

**Gut microbiome structure and metabolic activity in inflammatory bowel disease**

*Nat. Microbiol.* 2019; **4**:293-305

. This included 155 patients from the MGH PRISM cohort and 65 patients from two separate cohorts in the Netherlands. Similarly, annotated fecal metabolomic abundances, fecal calprotectin data and raw sequences were obtained. Raw sequences were again parsed through the same *de novo* assembled gene catalogue previously described to map for Bai enzyme homologues. Fecal measurements of secondary bile acids (deoxycholic acid, tauro-lithocholic acid, ursodeoxycholic acid) were then compared between *bai+* and *bai* - patients. Subsequently secondary bile acids, in particular deoxycholic acid, were compared between active and inactive IBD patients using paired fecal calprotectin measurements as a surrogate marker of luminal inflammation with varying clinical cut-offs (i.e. <50, <100, <150) (

40.

Rubin, D.T. ∙ Ananthakrishnan, A.N. ∙ Siegel, C.A....

**Clinical Guideline: Ulcerative Colitis in Adults**

*Am J Gastroenterol.* 2019 Mar; **114** (3):384-413

).

## Acknowledgments

The authors thank participating patients and research staff at the MGH Crohn’s and Colitis center. The authors also thank Luke Besse for project management and making data available through the Sequence Read Archive (SRA) and both the Broad Institute Microbial ‘Omics Core and Broad metabolomics Core for help with sequencing data generation. The authors are also grateful to Heather Kang for editorial assistance with the manuscript and figures, as well as Melanie Schirmer for helpful discussion. This study was funded by the National Institutes of Health (RO1 AT009708, P30 DK043351, U19 AI142784, U19 AI110495 to R.J.X.; R21 DK127227 to A.N.A.), Crohn’s and Colitis Foundation Microbiome Initiative (R.J.X.), Crohn’s and Colitis Foundation Senior Research Award (A.N.A.), Center for Microbiome Informatics and Therapeutics (R.J.X.), Chleck Family Foundation (A.N.A.), and the National Medical Research Council (J.W.J.L.).

### Author contributions

A.N.A. and R.J.X. conceived and designed the study. A.N.A., N.B., H.K., R.J.X., W.L., H.L., and S.M.G., enrolled the patients and conducted sampling and clinical measures. C.C. generated the metabolomics data. J.W.J.L. and L.H., analyzed sequencing data from metagenomics, metabolomics, and proteomics. D.R.P. assembled and analyzed metagenomes for Bai enzyme-encoding species. J.W.J.L., D.R.P., A.N.A., H.V., and R.J.X. discussed results and wrote the paper. All authors read, discussed, and approved the final manuscript.

### Declaration of interests

R.J.X. is a consultant to Novartis and co-founder of Celsius Therapeutics and Jnana Therapeutics. A.N.A. serves as a scientific advisor to Abbvie, Sun Pharma, Ikena Therapeutics, and Gilead. J.L.W.J. is co-founder of AMILI and serves as a member of the scientific advisory board.

## Supplemental information (3)

[PDF (3.30 MB)](https://www.cell.com/cms/10.1016/j.chom.2021.06.019/attachment/ad72d702-1f8f-47d5-9905-e639810c4f9c/mmc1.pdf)

Document S1. Figures S1–S4 and Tables S1, S2, and S4

[File (33.23 KB)](https://www.cell.com/cms/10.1016/j.chom.2021.06.019/attachment/ecaad10a-d007-4662-9af5-041cd47c5bdf/mmc2.csv)

Table S3. Differential fecal and microbial features (microbial species, enzymes, metabolites, and proteins) associated with any endpoint (p < 0.05, q < 0.2), related to Figures 2, 3, and 4

[PDF (7.45 MB)](https://www.cell.com/cms/10.1016/j.chom.2021.06.019/attachment/3d947c74-d15f-41ce-a9b9-14addefc031a/mmc3.pdf)

Document S2. Article plus supplemental information