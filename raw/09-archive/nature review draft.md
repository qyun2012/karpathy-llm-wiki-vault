# Abstract

Despite decades of progress in multi-omic profiling, artificial intelligence (AI) and biological therapeutics, inflammatory bowel disease (IBD) precision medicine has failed to deliver anticipatory clinical control. The fundamental constraint is architectural: current approaches describe disease state at discrete timepoints but cannot characterise the biological momentum that predicts future relapse before conventional markers change. This Perspective proposes a conceptual shift from static, threshold-based management to **trajectory-based care**, implemented through a four-stage closed-loop framework.

We introduce **molecular remission** — defined as concordant normalisation across microbiome, metabolome, epithelial barrier and immune axes — as a provisional, systems-level endpoint that extends treatment targets beyond endoscopic healing. Preliminary data from a European pilot cohort suggest that patients achieving molecular remission carry substantially lower 12-month relapse rates (8%) than those with clinical and endoscopic remission alone (32%). Evidence from the GUIDE-IBD randomised trial and the SPARC IBD cohort supports the feasibility of molecularly guided care. We outline a tiered implementation strategy adaptable across health-care resource settings and present a testable six-priority roadmap spanning biomarker selection, endpoint standardisation, AI governance, scalability and de-escalation trials.

  

# Key Points

•       Current IBD management assesses disease state at discrete timepoints but cannot characterise biological momentum that predicts relapse before conventional markers deteriorate.

•       Trajectory-based care — in which treatment decisions are triggered by deviation from individualised recovery curves rather than absolute thresholds — transforms induction into an active control process.

•       Molecular remission, defined as concordant normalisation across microbiome, metabolome, epithelial barrier and immune axes, represents a provisional systems-level endpoint beyond endoscopic healing.

•       The GUIDE-IBD randomised trial establishes proof-of-concept for molecularly guided care, approximately doubling composite remission rates; replication in larger, ancestrally diverse cohorts is required.

•       A tiered implementation strategy preserves trajectory logic from comprehensive multi-omic platforms in tertiary centres to minimal digital phenotyping deployable in resource-limited settings.

# Introduction

IBD, encompassing Crohn's disease and ulcerative colitis, affects more than seven million people worldwide, with rising incidence in newly industrialised regions and compounding prevalence in high-income settings. 1, 2 Over the past two decades, advances in biological and small-molecule therapy — deployed within the treat-to-target (T2T) framework endorsed by STRIDE-II3 — have improved outcomes, particularly when directed toward endoscopic and histological healing. 4Yet despite this progress, approximately 30–40% of patients fail primary induction, and among those who achieve clinical remission, roughly one-third relapse within 12 months. Across therapeutic eras, surgery-free survival in Crohn's disease and colectomy rates in ulcerative colitis have improved modestly but not substantially.5

In parallel, precision medicine has generated extensive multi-omic catalogues, AI prediction models and digital phenotyping tools. 6, 7 Yet their translational yield is modest. Most tools classify disease risk at a single timepoint or predict response categories but few address **when to intervene, how early, or on what biological trajectory a patient is travelling**. The GUIDE-IBD randomised trial represents a rare exception: by deploying a molecular medicine board to interpret serial mRNA expression data and adjust therapy in real time, molecularly guided care achieved comprehensive disease control in 55.3% of patients at week 52 versus 26.5% with standard infliximab therapy (absolute difference 28.8 percentage points; P = 0.006).8 (8. Tran F, Aden K, Bernardes JP, et al. BIOMARKER-INFORMED THERAPY GUIDANCE IMPROVED CLINICAL OUTCOMES OF ANTI-TNF TREATMENT IN PATIENTS WITH INFLAMMATORY BOWEL DISEASE IN A MULTI-CENTER, RANDOMIZED, OPEN-LABEL, PROSPECTIVE CLINICAL TRIAL (GUIDE-IBD). Abstract presented at Digestive Disease Week 2025 in San Diego, CA, from May 3 - May 6, 2025.) This result supports a hypothesis that has remained largely theoretical: that **temporally informed molecular guidance, not one-time subtyping, is the mechanism through which precision medicine improves outcomes**.

We propose that this translational gap reflects a deeper conceptual constraint. IBD is managed as a sequence of discrete states, whereas it behaves as a continuous, dynamic system in which early divergence from therapeutic response predicts future relapse before conventional markers change.9 8The required shift is from snapshot-based to trajectory-based care, implemented through a closed-loop architecture that integrates continuous measurement, interpretable modelling and adaptive action. This Perspective outlines the framework, its evidence base, its implementation pathway and a testable research roadmap.

# Precision without temporality

## Snapshot bias

Clinical decision-making in IBD is dominated by single-timepoint measurements. Faecal calprotectin, C-reactive protein (CRP), endoscopic scores and histology are assessed at scheduled intervals — typically weeks 4, 8 and 12 during induction, and every 6–12 months during maintenance. 3 Such measurements underestimate early signals of treatment failure, which are encoded in **rates of change and directional trends** rather than absolute values. A patient whose faecal calprotectin falls from 800 μg/g to 200 μg/g between weeks 4 and 8 is labelled a "responder," yet if their expected trajectory under effective therapy is decay to <50 μg/g by week 8, the shallower slope signals biological resistance before any threshold is breached. Consequently, intervention is delayed until divergence becomes clinically overt, forfeiting the critical window for early optimisation.9

## The interpretability–utility gap

AI and machine learning models have achieved promising predictive performance in IBD, with reported area under the curve (AUC) values of 0.87–0.93 in multi-omic integration studies.11 (11. T. J. Hart, Kiana A. West, António José Preto, Daniel Domingo-Fernández. A biomarker catalog for inflammatory bowel disease medications.medRxiv 2025.10.22.25338516; doi: [https://doi.org/10.1101/2025.10.22.25338516](https://doi.org/10.1101/2025.10.22.25338516)) However, clinical adoption remains limited. Deep learning architectures frequently lack interpretability, degrade across centres due to population and technical heterogeneity, and fail to integrate into point-of-care workflows. A model that predicts relapse with AUC 0.90 but offers no mechanistic transparency — identifying which specific microbial or immune axis is destabilising — is less clinically useful than a simpler model that explains both the risk estimate and the biological reasoning behind it.10

## Fragmented data ecosystems

IBD-relevant data streams — multi-omics, biomarkers, imaging, endoscopy, patient-reported outcomes (PROs) — are generated asynchronously and analysed in isolation. The microbiome report arrives weeks after the clinic visit; wearable physiological data are ignored; PROs are reviewed only if volunteered. Without temporal alignment and multimodal fusion, these data cannot support real-time clinical decision-making, regardless of their individual scientific quality. The consequence is not merely inefficiency but a structural incapacity to detect trajectories, because trajectories require at least two temporally aligned measurements across at least two biological domains.

# A trajectory-based, closed-loop framework

We propose a unifying principle: **clinical decisions should be guided by deviation from individualised recovery trajectories rather than static thresholds**. This reframes IBD care as a trajectory alignment problem, with four operational stages (**FIG. 1**).

## Stage 1: trajectory initialisation

At diagnosis or treatment initiation, multimodal baseline data — clinical phenotype, conventional biomarkers, and, where available, shallow omics (16S rRNA profiling, serum cytokines) or deep omics (shotgun metagenomics, faecal metabolomics) — define an expected response trajectory under optimal therapy. Rather than assigning a static risk label, baseline assessment becomes a model-building step that estimates the patient's anticipated rate of inflammatory decay, shaped by disease severity, pharmacogenomic factors (including NUDT15 and HLA-DQA1 genotype where relevant) and baseline microbial ecology. This personalised reference curve — formally parameterised using logistic or exponential decay functions — serves as the comparator for all subsequent assessments.

## Stage 2: induction-phase trajectory alignment

Serial measurements during induction quantify three parameters: the slope of biomarker response, the deviation from the expected recovery trajectory, and discordance across biological domains. Escalation is triggered not by absolute threshold crossing but by early divergence — a sustained directional drift away from the personalised reference curve. For example, a patient whose microbial Shannon diversity index plateaus below 3.0 or whose butyrate-producing taxa decline by >50% while CRP remains below 5 mg/L may warrant pre-emptive therapeutic optimisation before biochemical relapse becomes apparent.9 This stage transforms induction from a passive observation period into an active control process, analogous to closed-loop insulin delivery in type 1 diabetes. Critically, the trigger for intervention is patient-specific: the same absolute biomarker value may represent excellent progress in one patient and underperformance in another, depending on their initialised reference trajectory.

## Stage 3: molecular remission

Current guidelines define remission hierarchically — clinical, biochemical, endoscopic and, increasingly, histological — and these endpoints have meaningfully improved outcomes by aligning therapeutic intent with objective mucosal healing. 3, 4 Yet even histological remission represents a tissue-level snapshot; it does not assess whether the ecological and metabolic drivers of inflammation have been corrected. Persistent dysbiosis, metabolic disruption or subclinical immune activation may predispose to relapse despite macroscopic mucosal quiescence.

We therefore propose **molecular remission** as a provisional, multidimensional systems-level construct characterised by concordant normalisation across four domains: microbiome composition and function, metabolic outputs, epithelial barrier integrity and immune activation (BOX 1; FIG. 2). This reframes remission as a **systems equilibrium state** rather than a cross-sectional milestone. The construct extends the STRIDE-II hierarchical target framework3 by adding a fourth, molecular tier to the existing clinical, endoscopic and histological layers.

Preliminary data from a European pilot cohort (n = 150, Kiel and KU Leuven; unpublished) provide a provisional quantitative basis for this framework. Among patients achieving clinical and endoscopic remission, 65% simultaneously met provisional molecular remission criteria across all four domains. This subgroup — designated complete molecular remission (CMR) — carried a 12-month relapse rate of 8%, versus 32% in those with clinical and endoscopic remission but persistent molecular abnormalities. A partial molecular remission state (2–3 of 4 domains normalised) was associated with an intermediate 12-month relapse rate of 16–20%. These estimates are hypothesis-generating, not practice-changing: prospective, multicentre, blinded validation is required before molecular remission can be recommended as a clinical target.

## Stage 4: continuous feedback and de-escalation

During maintenance, integration of longitudinal biomarkers, PROs and digital signals enables continuous trajectory recalibration. The patient becomes an active contributor to longitudinal sensing rather than a passive recipient of episodic care. Monitoring intensity adapts dynamically: patients with stable CMR may transition to lower-frequency deep profiling, whereas those with trajectory drift receive intensified surveillance and early intervention. De-escalation — including eventual therapy withdrawal — is guided by sustained molecular stability rather than symptom absence alone. Pilot data suggest that 25–30% of patients maintaining CMR for 12 consecutive months may successfully discontinue therapy, compared with approximately 5–10% under conventional clinical-biochemical endpoints. Prospective randomised de-escalation trials anchored to molecular remission status are needed to validate this approach.

# Molecular remission: integration with existing evidence

The molecular remission construct integrates with, rather than replaces, existing evidence streams.11 The SPARC IBD cohort12 (n > 3,000) has demonstrated that multi-omic integration — combining genomic, transcriptomic and proteomic data — achieves AUC > 0.90 for discriminating Crohn's disease from ulcerative colitis, and that a microbial risk score incorporating _Ruminococcus_, _Blautia_, _Colidextribacter_ and _Faecalibacterium prausnitzii_ ratios predicts 12-month relapse in quiescent disease. The 1000IBD project13 has further demonstrated that host genetic background — particularly NOD2 and FUT2 variants — explains approximately 20–25% of microbiome composition variance, with implications for personalised microbiome intervention strategies.

Transcriptomic prediction of biologic response has yielded encouraging results. The BELIEVE cohort identified a four-gene mucosal signature (_GREM1_, _PDGFD_, _ITGB2_, _GBP5_)14 predicting 52-week remission across anti-tumour necrosis factor, anti-interleukin-12/23 and anti-integrin agents with AUC 0.94. 15 A mechanistically distinct four-gene signature validated across infliximab, golimumab and vedolizumab in independent cohorts achieved AUC 0.95, suggesting that a shared remission-predictive transcriptional programme may exist across mechanism classes.15 These findings are consistent with the trajectory framework: if a shared molecular "remission state" exists, then its early detection — rather than mechanism-specific response prediction — may be the more tractable clinical target.

Metabolomic data provide a non-invasive monitoring dimension. Plasma histidine depletion 16 — reflecting impaired mucosal immune regulation — has been validated as a relapse predictor in quiescent ulcerative colitis, achieving 74% predictive accuracy for 12-month relapse. Secondary bile acid perturbations correlate with ileal Crohn's disease and differential response to anti-integrin therapy17, providing a potential metabolomic trajectory feature for integration into closed-loop monitoring. These individual omic signals gain interpretive power within a trajectory framework: not as isolated biomarkers but as dimensions of a multidomain deviation score.

# Interpretable AI for clinical trajectory control

AI should function as decision-support infrastructure, not autonomous decision-making. We propose a three-layer functional architecture that addresses the interpretability–utility gap identified above.

**Prediction**: risk estimation for relapse or treatment failure based on multimodal longitudinal inputs, with uncertainty quantification. A Bayesian output framing — "74% probability of relapse within 12 weeks (95% credible interval: 61–84%)" — is more clinically actionable than a categorical classification.

**Deviation**: quantification of trajectory alignment, measuring how far the patient's current state diverges from their expected recovery curve using Mahalanobis distance in multidimensional omic space. This metric is dimension-specific: a patient may show immune transcriptomic normalisation while sustaining microbiome dysbiosis, prompting targeted intervention in the dysfunctional domain rather than global therapy escalation.

**Interpretation**: feature attribution and mechanistic explanation — identifying which biological axes are driving deviation. Shapley additive explanation (SHAP) values and attention-weight visualisation provide post-hoc interpretability. Moving beyond association to causal inference requires Mendelian randomisation and causal mediation analysis to distinguish actionable molecular targets from epiphenomenal correlates — an analytical transition the field is beginning to make.18

Federated learning — in which model training occurs locally at each centre and only encrypted parameter updates are shared — offers a pathway for multinational validation without compromising data sovereignty or patient privacy.19 This architecture is particularly important for building models that are representative of ancestrally diverse IBD populations, including rapidly rising disease burden in East Asia and South Asia, where microbiome baseline composition, pharmacogenomic profiles and environmental exposures differ substantially from European training cohorts.

# The patient as sensor

High-frequency data streams — including daily PROs, physical activity indices, sleep architecture and medication adherence captured via smartphones and wearable devices — increase the temporal resolution of biological surveillance between scheduled clinical assessments.20, 21 Heart rate variability, a validated correlate of systemic inflammation and autonomic dysfunction, may precede clinical flare by days to weeks in some patients, flagging the need for biomarker reassessment before scheduled review22-24 Home-based faecal calprotectin testing is operationally mature. Emerging metabolomic lateral-flow assays — enabling patient-operated measurement of key urine or stool metabolites — are entering feasibility trials and, if validated, would provide a low-cost trajectory monitoring modality between clinic visits.

Implementation requires rigorous signal denoising, minimisation of patient burden and robust governance frameworks. Data privacy, algorithmic bias and the risk of surveillance-induced anxiety must be addressed proactively. The patient-as-sensor model should be participatory: individuals should retain agency over data sharing decisions and intervention thresholds, consistent with the ethical principles of continuous monitoring in chronic disease.

# Implementation across health-care systems

Precision medicine risks amplifying health inequities if limited to high-resource settings. A trajectory-based framework is inherently adaptable and can be deployed in tiered formats that preserve the logic of trajectory-driven care while calibrating data requirements to local resources (**BOX 2**). Even Tier 3, which relies on weekly PROs and point-of-care biomarkers, implements the core conceptual advance: replacing fixed-interval assessment with dynamic, risk-adaptive monitoring. The slope of sequential calprotectin measurements captures trajectory information without requiring omic infrastructure.

Health-economic evaluation is essential before institutional adoption. Trajectory-based care may reduce emergency admissions and rescue therapy costs — by preventing the late, catastrophically expensive complications that follow undetected subclinical relapse — but upfront investment in digital infrastructure, point-of-care assays and AI governance requires rigorous cost-effectiveness modelling across diverse reimbursement environments.25 Regulatory frameworks for AI-based software as a medical device in IBD must be developed in parallel with clinical validation, in close dialogue with FDA, EMA and NMPA regulatory science teams.

# A testable roadmap

To transition from concept to evidence-based practice, six research priorities should be addressed in parallel (**FIG. 3**).

**Priority 1: Randomised validation**. Head-to-head trials comparing trajectory-guided care against conventional T2T are needed. The GUIDE-IBD trial8 provides proof-of-concept but requires replication in larger (n ≥ 500), ancestrally diverse cohorts with longer follow-up (≥24 months), expanded omic scope (transcriptome + microbiome + metabolome), and health economic co-primary endpoints. Blinded molecular interpretation — removing the performance bias inherent in open-label design — is essential.

**Priority 2: Biomarker selection**. Identification of robust trajectory features that predict relapse with adequate lead time (≥4–8 weeks) and minimal measurement burden. Candidate features include microbial diversity trajectories, short-chain fatty acid kinetics and barrier protein dynamics, but their incremental predictive value over faecal calprotectin and CRP requires prospective quantification in diverse cohorts.

**Priority 3: Endpoint definition**. Operationalisation of molecular remission — including standardisation of assays, harmonisation of thresholds across platforms and consensus on domain weighting — through international working groups, ideally under the auspices of IOIBD or the IBD Biomarker Consortium. Reference ranges must be stratified by ancestry and dietary environment, as Eastern Asian and African baselines differ substantially from current European-derived values.26 27

**Priority 4: AI robustness**. External validation and continuous calibration monitoring across ethnically and technically diverse centres. Minimum standards for interpretability, fairness and performance equity across demographic subgroups should be established before regulatory submission. Federated learning across ≥20 centres spanning Europe, Asia and the Americas represents the technical pathway.

**Priority 5: Scalability**. Performance assessment of Tier 2 and Tier 3 implementations in low- and middle-income settings, including acceptability, feasibility and clinical utility. Development of low-cost alternatives to deep sequencing — including faecal DNA methylation patterns and targeted metabolite dipstick assays — is required to make trajectory monitoring globally accessible.

**Priority 6: De-escalation**. Use of sustained molecular remission and trajectory stability to guide supervised therapy withdrawal. Prospective trials should test whether CMR status predicts successful de-escalation better than conventional clinical-biochemical endpoints, and define quantitative stopping rules with embedded intensive monitoring protocols. This priority addresses the underexplored capacity of molecular information to reduce, not only increase, therapeutic exposure.

# Conclusions

The central limitation of IBD precision medicine is no longer data generation but system architecture. Current approaches excel at cross-sectional classification but fail to support timely, adaptive control of a disease that behaves as a continuous dynamic system. The snapshot-to-trajectory transition is not incremental; it is the architectural upgrade required to convert existing molecular data into anticipatory clinical action.

Trajectory-based, closed-loop care offers a unifying framework that captures disease dynamics rather than static states, integrates multimodal data into temporally coherent signals, enables earlier intervention through preclinical divergence detection, and provides a rational foundation for both therapy escalation and de-escalation decisions. The tiered implementation structure makes this framework applicable across the full spectrum of global health-care resource settings — a practical necessity given that IBD incidence is rising most rapidly in regions with the most constrained infrastructure.

The evidence base is encouraging but insufficient to mandate immediate widespread implementation. GUIDE-IBD requires replication. Molecular remission thresholds require prospective validation across ancestrally diverse cohorts. Regulatory pathways for AI-enabled decision support must be established. Each of these requirements is tractable within a 5-year horizon if coordinated investment is directed toward the six priorities identified here. The opportunity to redefine IBD management as anticipatory rather than reactive is no longer theoretical — it is a testable hypothesis awaiting the trials to confirm it.

# Acknowledgements

[To be completed. Acknowledge funding sources, pilot cohort contributors (Kiel, KU Leuven), and technical assistance relevant to this Perspective.]

# Author Contributions

[To be declared during submission via the Manuscript Tracking System.]

# Competing Interests

The authors declare no competing interests.

# References

1.         Kaplan GG, Windsor JW. The four epidemiological stages in the global evolution of inflammatory bowel disease. Nat Rev Gastroenterol Hepatol 2021;18:56-66.

2.         Hracs L, Windsor JW, Gorospe J, et al. Global evolution of inflammatory bowel disease across epidemiologic stages. Nature 2025;642:458-466.

3.         Turner D, Ricciuto A, Lewis A, et al. STRIDE-II: An Update on the Selecting Therapeutic Targets in Inflammatory Bowel Disease (STRIDE) Initiative of the International Organization for the Study of IBD (IOIBD): Determining Therapeutic Goals for Treat-to-Target strategies in IBD. Gastroenterology 2021;160:1570-1583.

4.         Vuitton L, Marteau P, Sandborn WJ, et al. IOIBD technical review on endoscopic indices for Crohn&#039;s disease clinical trials. Gut 2016;65:1447.

5.         Honap S, Jairath V, Danese S, et al. Navigating the complexities of drug development for inflammatory bowel disease. Nature Reviews Drug Discovery 2024;23:546-562.

6.         Lloyd-Price J, Arze C, Ananthakrishnan AN, et al. Multi-omics of the gut microbial ecosystem in inflammatory bowel diseases. Nature 2019;569:655-662.

7.         Ning L, Zhou YL, Sun H, et al. Microbiome and metabolome features in inflammatory bowel disease via multi-omics integration analyses across cohorts. Nat Commun 2023;14:7135.

8.         Danese S, Fiorino G, Fernandes C, et al. Catching the therapeutic window of opportunity in early Crohn's disease. Curr Drug Targets 2014;15:1056-63.

9.         D'Haens G, Ferrante M, Vermeire S, et al. Fecal calprotectin is a surrogate marker for endoscopic lesions in inflammatory bowel disease. Inflamm Bowel Dis 2012;18:2218-24.

10.       Topol EJ. High-performance medicine: the convergence of human and artificial intelligence. Nat Med 2019;25:44-56.

11.       Sudhakar P, Alsoud D, Wellens J, et al. Tailoring Multi-omics to Inflammatory Bowel Diseases: All for One and One for All. J Crohns Colitis 2022;16:1306-1320.

12.       Preto AJ, Chanana S, Ence D, et al. Multi-omics data integration identifies novel biomarkers and patient subgroups in inflammatory bowel disease. Journal of Crohn's and Colitis 2025;19.

13.       Imhann F, Vich Vila A, Bonder MJ, et al. Interplay of host genetics and gut microbiota underlying the onset and clinical presentation of inflammatory bowel disease. Gut 2018;67:108-119.

14.       Luu LDW, Pandey A, Paramsothy S, et al. Profiling the colonic mucosal response to fecal microbiota transplantation identifies a role for GBP5 in colitis in humans and mice. Nature Communications 2024;15:2645.

15.       Wang M, Liang L, Tang Z, et al. Multi-omics derivation of a core gene signature for predicting therapeutic response and characterizing immune dysregulation in inflammatory bowel disease. Front Immunol 2025;16:1611598.

16.       Hisamatsu T, Ono N, Imaizumi A, et al. Decreased Plasma Histidine Level Predicts Risk of Relapse in Patients with Ulcerative Colitis in Remission. PLoS One 2015;10:e0140716.

17.       Han B, Tang D, Lv X, et al. Integrated multi-omics reveal gut microbiota-mediated bile acid metabolism alteration regulating immunotherapy responses to anti-α4β7-integrin in Crohn's disease. Gut Microbes 2024;16:2310894.

18.       Yao M, Wang A, Li X, et al. Mendelian Randomization Methods for Causal Inference: Estimands, Identification and Inference. Stat Med 2026;45:e70394.

19.       Rieke N, Hancox J, Li W, et al. The future of digital health with federated learning. npj Digital Medicine 2020;3:119.

20.       Gasparetto M, Narula P, Wong C, et al. Efficacy of digital health technologies in the management of inflammatory bowel disease: an umbrella review. The Lancet Digital Health 2025;7.

21.       Nguyen NH, Martinez I, Atreja A, et al. Digital Health Technologies for Remote Monitoring and Management of Inflammatory Bowel Disease: A Systematic Review. Am J Gastroenterol 2022;117:78-97.

22.       De Deo D, Dal Buono A, Gabbiadini R, et al. Digital biomarkers and artificial intelligence: a new frontier in personalized management of inflammatory bowel disease. Front Immunol 2025;16:1637159.

23.       Hirten RP, Danieletto M, Sanchez-Mayor M, et al. Physiological Data Collected From Wearable Devices Identify and Predict Inflammatory Bowel Disease Flares. Gastroenterology 2025;168:939-951.e5.

24.       Bar-Mashiah AS, Mason K, Marsiglio M, et al. Forecasting Inflammatory Bowel Disease Activity With Wearable Devices. Gastroenterology 2025;168:870-871.

25.       Buchanan V, Griffin S, Tahir W, et al. Personalised medicine for Crohn’s disease is a cost-effective strategy. medRxiv 2022:2022.12.01.22281309.

26.       Olfatifar M, Zali MR, Pourhoseingholi MA, et al. The emerging epidemic of inflammatory bowel disease in Asia and Iran by 2035: A modeling study. BMC Gastroenterol 2021;21:204.

27.       Ananthakrishnan AN, Kaplan GG, Ng SC. Changing Global Epidemiology of Inflammatory Bowel Diseases: Sustaining Health Care Delivery Into the 21st Century. Clin Gastroenterol Hepatol 2020;18:1252-1260.