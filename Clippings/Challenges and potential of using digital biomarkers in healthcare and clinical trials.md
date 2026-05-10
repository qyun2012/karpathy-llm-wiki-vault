---
title: "Challenges and potential of using digital biomarkers in healthcare and clinical trials"
source: "https://www.nature.com/articles/s43856-026-01450-8"
author:
  - "[[Johann K. Lieberwirth]]"
  - "[[Mirja Mittermaier]]"
  - "[[Ariel Dora Stern]]"
published: 2026-02-21
created: 2026-05-05
description: "Digital biomarkers use sensors and analytics, to offer continuous monitoring and personalized medicine. In this Perspective, we describe real-world use cases, such as glucose tracking to optimise insulin dosing and wearables to measure heart rhythms to de-risk cardiovascular trials. We also discuss the issues preventing most candidate biomarkers from reaching clinical practice. Evidence generation is costly, regulatory reviews can be redundant, commercial incentives fall short, and data silos can be biased and/or nonrepresentative. By combining harmonized qualification pathways, value-based reimbursement, modular extensions for single-trial biomarkers, and adaptive post-market evidence loops, we propose a path from experimental signal to standard of care. Lieberwirth et al. discuss the current landscape of digital biomarkers in healthcare and clinical trials, highlighting growth in the use of digital endpoints and the emergence of dedicated “digital biomarker” startups. They discuss key barriers to translation and outline practical priorities for wider adoption."
tags:
  - "clippings"
---
## Abstract

Digital biomarkers use sensors and analytics, to offer continuous monitoring and personalized medicine. In this Perspective, we describe real-world use cases, such as glucose tracking to optimise insulin dosing and wearables to measure heart rhythms to de-risk cardiovascular trials. We also discuss the issues preventing most candidate biomarkers from reaching clinical practice. Evidence generation is costly, regulatory reviews can be redundant, commercial incentives fall short, and data silos can be biased and/or nonrepresentative. By combining harmonized qualification pathways, value-based reimbursement, modular extensions for single-trial biomarkers, and adaptive post-market evidence loops, we propose a path from experimental signal to standard of care.

Biomarkers are defined by the U.S. Food and Drug Administration (FDA) and the U.S. National Institutes of Health (NIH) as characteristics that can be measured to indicate normal biological processes, pathogenic processes, or responses to an exposure or intervention, including therapeutic interventions [^1]. Traditional biomarkers, such as blood glucose levels or heart rate, have long been key to medical practice, serving as diagnostic, prognostic, or predictive tools [^1] [^2]. In recent years, the integration of digital biomarkers in the healthcare delivery and clinical research settings has transformed both diagnostics and patient monitoring, enhancing the potential for early disease detection, personalized treatment, and continuous health monitoring.

Despite the increasing use of digital biomarkers, there is a notable lack of consensus on the definition of the term itself: a systematic review found that among 415 articles using the term “digital biomarker,” only 31% provided a clear definition, with 127 different definitions identified among those that did [^3]. This lack of standardization is further complicated by the overlap between digital biomarkers and other health metrics, such as clinical outcome assessments, leading to confusion and conflation in their usage [^4]. This variability complicates communication among researchers, clinicians, and regulators, highlighting the need for standardized terminology [^1] [^4] [^5].

For the purpose of this discussion, we adopt the definition provided by the European Medicines Agency (EMA): a digital biomarker is “an objective, quantifiable measure of physiology and/or behavior used as an indicator of biological, pathological process or response to an exposure or an intervention that is derived from a digital measure. The clinical meaning is established by a reliable relationship to an existing, validated endpoint” [^6]. This definition underscores the requirement that the data collection, processing, and analysis must be inherently digital.

However, in some cases, this definition is not as clear as might be desired, as most biomarkers involve some degree of digital data processing in practice. We illustrate this by considering two examples, prostate-specific antigen (PSA) and continuous glucose monitoring (CGM).

PSA testing involves manual blood sample collection and biochemical assays, with digital technology applied only during data reporting. Therefore, PSA is not considered a digital biomarker under the EMA’s definition, as the measurement is not derived from a digital measure.

In contrast, CGM devices continuously monitor glucose levels through sensors that convert biochemical signals into digital data. Despite the initial biochemical interaction, CGM-derived glucose readings are considered digital biomarkers because the data collection, processing, and analysis are inherently digital. Integrating biochemical sensing with digital technology enables continuous monitoring and data-driven insights, aligning CGMs with the EMA’s definition of digital biomarkers.

The biomarkers, endpoints, and other tools (BEST) glossary developed by the FDA and NIH categorizes biomarkers into several subgroups based on their specific applications in healthcare and research, highlighting the broad spectrum of possible applications for biomarkers [^1]. Table [1](https://www.nature.com/articles/s43856-026-01450-8#Tab1) presents examples of both traditional and digital biomarkers in each respective subgroup. A comprehensive version of this table, including definitions, can be found in Supplementary Data [1](https://www.nature.com/articles/s43856-026-01450-8#MOESM2).

**Table 1 Biomarker definitions and examples**

## Clinical benefits and general opportunities

The European Union defines personalized medicine as “a medical model using characterization of individuals’ phenotypes and genotypes (e.g., molecular profiling, medical imaging, lifestyle data) for tailoring the right therapeutic strategy for the right person at the right time, and/or to determine the predisposition to disease and/or to deliver timely and targeted prevention” [^7]. Biomarkers underpin this model by informing clinical decisions [^8] [^9]. Digitally captured biomarkers amplify this concept: everyday devices gather continuous, non-invasive data, making large-scale, low-cost screening feasible and shifting detection to pre-symptomatic stages. Examples include fall-risk alerts derived from gait data on smartphones, sleep-apnea screening via wearables, and mobile ECGs to detect atrial fibrillation, where traditional screening is limited by cost constraints [^10].

Continuous monitoring is particularly promising for the management of chronic diseases. Wearable devices and smart inhalers can track respiratory rates, airflow, and oxygen saturation in COPD and asthma patients, detecting exacerbations before symptoms become severe and help monitor therapy adherence [^11] [^12] [^13] [^14]. In diabetes, continuous glucose monitors provide real-time blood sugar trends for better insulin regulation [^15] [^16], while subtle changes in voice, body weight, or physical activity can indicate worsening heart failure, prompting timely intervention [^17]. Indeed, conditions requiring precise dosage adjustments are better managed through real-world, ambulatory data rather than relying solely on intermittent clinic visits [^15] [^18] [^19] [^20].

For conditions with fluctuating severity, such as mental health disorders, passive monitoring of speech patterns, phone usage, and physical activity can detect early signs of mood changes, facilitating timely intervention [^21]. This continuous, unobtrusive monitoring provides a more objective and nuanced understanding of symptom severity than traditional self-reporting.

Fields such as cardiology, endocrinology, neurology, and psychiatry are thus particularly poised to benefit from these innovations, as these represent settings in which continuous, objective ambulatory measurements can enable early detection, real-time monitoring, and personalized intervention. This is also reflected by the distribution of medical specialties represented by studies in the Digital Medicine Society’s *Library of Digital Endpoints* (DiMe *LDE*) [^22] (for more details, refer to the next section). By improving both the precision of diagnosis and the timeliness of care, digital biomarkers pave the way for a shift from reactive to proactive and preventive healthcare, ultimately enhancing patient outcomes.

## Opportunities in drug development and clinical trials

Biomarkers are utilized throughout the process of clinical development to reduce uncertainty and enhance the efficacy of decision-making. They have the capacity to facilitate enrichment and stratified analyses, provide early pharmacodynamic evidence of target engagement and dose response, monitor safety, and—in certain circumstances—act as surrogate endpoints when adequately validated for a defined context of use. In this section, the general trial functions are first outlined, and then the focus shifts to the extension of these functions using digital biomarkers, which enable remote, high-frequency measurements in real-world settings.

The cost of drug development is now estimated to exceed $1 billion per approved drug, with fewer than 1% of early-stage candidates reaching market approval [^23] [^24], and the number of FDA-approved drugs per billion U.S. dollars spent halving approximately every nine years [^23]. Late-stage clinical trial failures have contributed to declining success rates, underscoring the urgency for more efficient trial methodologies. Insufficient efficacy is the predominant reason for candidate failure, highlighting the need for both improved patient stratification and trial design [^25].

Biomarker-driven assessments in Pfizer’s clinical trials increased phase II success rates from 19 to 53%, substantially reducing costly late-stage failures [^26]. By enabling early proof-of-mechanism studies, optimizing dosing, and improving patient stratification, biomarkers helped limit the number of ineffective compounds advancing to phase III. This experience highlights the growing importance of biomarker integration in clinical trial design [^26].

Biomarkers serve as critical tools in optimizing clinical trials and, therefore, new therapeutic development by refining patient selection and increasing the probability of therapeutic success [^8]. Stratification based on biomarkers enhances the detection of clinically meaningful effects in specific subpopulations. Previous studies have shown that biomarkers—and, increasingly, digital endpoints—can significantly reduce cohort sizes, shorten study duration, and increase success rates [^27] [^28] [^29]. These efficiency gains directly translate to reduced costs and accelerated timelines for drug approval [^30].

Beyond improving efficiency, biomarkers provide essential mechanistic insights that inform drug development strategies. Retrospective analyses enable the identification of responsive subpopulations, justifying continued investment in promising compounds [^8]. Although this approach necessitates additional upfront costs for sample collection and storage, it can potentially salvage projects that might otherwise be terminated due to apparent inefficacy.

Even when clinical trials fail, biomarkers can provide actionable insights. If a biomarker confirms full target engagement but no therapeutic benefit is observed, this suggests that the drug’s molecular target is not a key driver of the disease [^8] [^26]. Conversely, insufficient target engagement may indicate inadequate drug potency, bioavailability, or dosing, rather than a fundamental failure of the therapeutic approach. These insights refine future drug development strategies, benefiting not only the immediate stakeholders but also the broader biomedical research and development community [^8] [^31].

Digital biomarkers represent a subset of biomarkers derived from digital measures and digital health technologies, allowing continuous or frequent remote data capture that can support decentralized trial designs and potentially improve efficiency and participant experience. A study analyzing trials from the DiMe *LDE* found that Phase III trials incorporating digital biomarkers were, on average, 4–5 months shorter and had 11.7% fewer participants. The average return on investment of initial implementation costs of digital endpoints ranged between 31 and 48% for phase II trials and 350 and 590% for phase III trials [^32].

The scale of potential efficiency gains is striking [^33]. Holding 80% power, a 30% effect size, and a four-year horizon constant, conventional memory testing required an estimated 2000 participants; a digital gait outcome reduced the need to 262, and a computer-use endpoint to 26. By capturing high-frequency behavior in naturalistic, real-world settings, digital biomarkers can deliver orders-of-magnitude reductions in sample size, with direct implications for timelines and cost.

Digital biomarkers are revolutionizing decentralized clinical trials (DCTs) by minimizing dependence on centralized research facilities and leveraging home-based data collection through wearables and telemedicine [^34]. These typically passive measurements demand little to no effort from patients, significantly enhancing adherence, particularly among populations with historically lower compliance [^35] [^36]. Unlike traditional trials, which are reliant on sporadic clinic visits, DCTs enable continuous or frequent data collection, yielding richer datasets and more reliable insights with fewer clinic visits. Beyond logistical advantages, DCTs improve trial efficiency on multiple fronts. They facilitate faster participant recruitment, bolster retention rates, and enhance patient autonomy and convenience. Additionally, by lowering enrollment barriers, DCTs contribute to greater trial diversity, ensuring outcomes that are more representative of real-world populations [^36].

At the time of analysis, the DiMe *LDE* cataloged 102 clinical trials employing digital endpoints, with 44 using them as primary measures and 79 incorporating them as secondary endpoints [^22]. The majority of these trials focus on endocrine/metabolic (30.4%) and neurological conditions (24.5%), followed by cardiovascular, respiratory, and mental health disorders (Fig. [1](https://www.nature.com/articles/s43856-026-01450-8#Fig1)). The increasing prevalence of digital biomarkers in clinical trials reflects improved feasibility of remote, high-frequency data capture, the advancement of digital health technologies in recent years, and the practical appeal of more convenient data collection approaches.

![Fig. 1: Clinical trials using digital endpoints over time, by condition category (2005–2024)](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fs43856-026-01450-8/MediaObjects/43856_2026_1450_Fig1_HTML.png?as=webp)

Fig. 1: Clinical trials using digital endpoints over time, by condition category (2005–2024)

## Challenges and regulatory considerations

The path from digital biomarker discovery to clinical use is marked by significant translational barriers. Most biomarkers do not advance from research settings to regulatory approval and broad clinical implementation, in part owing to complex validation protocols, stringent regulatory requirements, and integration challenges within healthcare infrastructure [^37] [^38] [^39]. Regulatory pathways, particularly “biomarker qualification programs” from regulators, such as the FDA and the EMA, that enable broad use across different contexts of use, remain complex and slow, with only a few biomarkers successfully qualified to date [^40] [^41]. Consequently, many biomarkers are confined to single-trial validation, limiting their broader impact.

These system-level obstacles are compounded by measurement-specific issues. Ensuring that digital biomarkers are both methodologically robust and clinically meaningful requires adherence to rigorous evidence-generation frameworks, such as the Verification-Analytical Validation-Clinical Validation (V3) paradigm [^5]. Unlike many traditional biomarkers, such as genetic mutations and blood tests, that have direct mechanistic links to disease pathology and well-established reference standards, digital biomarkers are derived from sensors and algorithms and often must be interpreted within a defined clinical context. The V3 framework structures this work into three linked questions:

- *Verification*: do sensors and devices meet predefined technical specifications and reliably capture the intended raw signal? Example: bench testing an accelerometer-based system to confirm accurate motion capture under controlled conditions.
- *Analytical validation*: do the algorithms transform raw signals into accurate, reproducible measures? Example: comparing algorithm-derived step counts with a gold-standard manual tally and assessing agreement, repeatability, and drift.
- *Clinical validation*: does the resulting measure answer a specific clinical question in its context of use? Example: testing whether step-count or gait metrics predict mobility improvement in patients undergoing rehabilitation or track clinically meaningful change over time.

Additional challenges arise from symptom variability across patients. In diseases such as Parkinson’s, Alzheimer’s, or depression, symptoms manifest differently and fluctuate over time. A biomarker that reliably detects tremor in one subgroup of Parkinson’s patients may not apply to those whose dominant symptoms are rigidity or bradykinesia. As a result, analyses may need to be stratified by phenotype or symptom domain to avoid misleading conclusions. Day-to-day variation related to medication cycles, stress, or fatigue further complicates validation and reproducibility.

A further issue is the absence of gold standards for many digital biomarkers [^38]. Unlike traditional biomarkers with well-established reference measures, such as red blood cell counts in anemia, digital biomarkers often lack direct clinical equivalents. For example, a tool that detects vocal markers of depression must be compared to clinical assessments rather than objective biological markers, complicating accuracy targets and thresholds. Context dependence adds another layer: digital biomarkers may capture proxy variables rather than the condition itself. A wearable detecting reduced hand movement may suggest Parkinson’s, but could also indicate arthritis or fatigue.

Even when a digital measure detects a pattern, it must be clinically validated against outcomes that matter to patients. The FDA’s initial rejection of the Verily study watch for Parkinson’s illustrates this challenge: despite alignment with the Movement Disorder Society-Unified Parkinson’s disease rating scale (MDS-UPDRS), it was deemed insufficient for capturing meaningful patient function. These difficulties are especially pronounced in neurodegenerative and psychiatric diseases, where symptom expression is heterogeneous and hard to standardize. To mitigate this, a framework has been proposed that anchors digital measures to patient-relevant outcomes, improving the likelihood of regulatory and clinical acceptance [^42].

### Practical considerations in population screening

Beyond therapeutic applications, digital biomarkers are increasingly deployed for early disease detection and broad population screening. As with every test, false positives can lead to unnecessary follow-up tests and treatments, while false negatives risk preventing individuals who need timely intervention from seeking professional evaluation. Even when these tests perform well, they can introduce new challenges: there is a growing number of asymptomatic individuals, often significantly younger than the average cardiac patient, alerted by their smartwatches about intermittent atrial fibrillation. For this population, the benefits of anticoagulant therapies remain unclear, raising concerns about how to appropriately address these findings in practice and their broader implications for public health [^10] [^43] [^44].

### Algorithmic bias and healthcare inequities

Further ethical concerns emerge regarding algorithmic bias and disparities in digital health access. Surveys indicate that individuals with higher income, higher education levels, and those residing in urban areas are more likely to own and use wearable devices [^45]. Developing digital health solutions primarily for these platforms without addressing barriers to access may exacerbate existing health inequities. Algorithmic bias in data processing and interpretation can disproportionately affect minority groups, necessitating rigorous fairness assessments in biomarker validation [^46]. A prominent example of this kind of bias is the underrepresentation of diverse skin colors in datasets used to train skin cancer detection algorithms, which can lead to biased predictions for underrepresented groups [^47].

### Misaligned financial incentives

Beyond these scientific and clinical challenges, financial incentives and regulatory hurdles further shape biomarker development [^48]. While biomarkers can enhance drug development and precision medicine, industry investment is driven by market dynamics, such as pricing strategies and competitive advantages [^49] [^50]. Predictive biomarkers inherently narrow a drug’s eligible patient pool, which threatens sales volumes, however, current reimbursement frameworks rarely allow higher prices to offset this loss, so manufacturers gain little financial return on the substantial R&D cost of biomarker development. Explicit pricing rewards or coverage incentives for precision-guided therapies, motivates drug companies to invest in validating and commercializing predictive biomarker tests [^49].

## Future directions, conclusions and recommendations

Looking ahead, advances in digital phenotyping and the use of patient “digital twins” could further support personalized healthcare. Digital phenotyping allows for the continuous, high-resolution monitoring of individual health trajectories through everyday digital interactions [^51]. Digital patient twins, virtual representations of an individual that are continuously updated with longitudinal, multi-source patient data (e.g., EHR, imaging, and wearable/IoT streams), coupled with computational models (often incorporating AI/ML), promise to refine treatment simulations and optimize intervention strategies [^52]. Their use will almost certainly increase as U.S. policy encourages pharmaceutical R&D to move away from the use of animal models in drug development [^53]. These technologies have far-reaching implications beyond clinical settings, extending to public health surveillance, occupational health, and actuarial modeling in the insurance sector.

The entrepreneurial landscape reflects this rapid development, with an increasing number of startups focusing on digital biomarkers (Fig. [2](https://www.nature.com/articles/s43856-026-01450-8#Fig2)). An analysis of venture-funded companies listed in PitchBook reveals that investment in this sector has surged, particularly between 2018 and 2021, driven by advances in wearable technology, data analytics, and personalized medicine [^54]. Although there has been a post-2021 funding slowdown due to broader market corrections, the continued interest in digital health solutions highlights the commercial potential of digital biomarkers.

![Fig. 2: Digital biomarker startup formation and share among biomarker companies (PitchBook, 2000–2024)](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fs43856-026-01450-8/MediaObjects/43856_2026_1450_Fig2_HTML.png?as=webp)

Fig. 2: Digital biomarker startup formation and share among biomarker companies (PitchBook, 2000–2024)

Despite their potential, significant challenges remain. Validation and standardization efforts are critical, as digital biomarkers often lack universally accepted benchmarks compared to traditional biomarkers. Regulatory uncertainty, ethical concerns related to data privacy and algorithmic bias, and potential healthcare inequities must be addressed to ensure fair and effective implementation.

In order to overcome the persistent barriers that currently exist, coordinated action is likely to be needed. In the immediate future, there are several pragmatic measures that must be taken by sponsors, investigators, and developers:

- *Adopt regulator-aligned terminology and ontology*: explicitly map key terms to the FDA BEST glossary and relevant EMA guidance in manuscripts and protocols (e.g., a short definitions table), avoiding trial-specific redefinitions.
- *Embed fit-for-purpose validation from the outset*: digital-biomarker programmes should adopt the V3 framework, a step-wise process that first confirms reliable signal capture, then demonstrates assay accuracy and reproducibility, and finally proves real-world clinical relevance [^5]. Implementing V3 at the concept stage ensures that algorithms, assay precision and patient benefit are established before large-scale deployment, thereby meeting the evidentiary thresholds that currently impede regulatory progress. Frameworks can help align digital endpoints with clinically meaningful outcomes, ensuring that validation demonstrates both clinical effect and patient-relevant benefit, thereby meeting regulatory requirements [^42].
- *Plan for re-use via comparability evidence*: when extending a single-trial biomarker to new contexts of use, maintain measurement consistency (sensor mechanism, device configuration, algorithm/software version) where feasible; when technology changes, pre-specify bridging/comparability testing to demonstrate analytical equivalence.
- *Institutionalize equity and bias safeguards*: pre-register bias audits (including subgroup performance), document training/validation dataset representativeness, and include an access plan (e.g., device provision/loan models) when endpoints rely on consumer hardware.

Longer-term needs (regulators/payers/health systems)

- *More predictable regulatory pathways*: expand and clarify qualification/acceptance routes for digital endpoints and define expectations for cross-trial re-use (including comparability requirements).
- *Reduce duplicative review across agencies*: explore mechanisms for regulatory reliance, shared scientific advice, or aligned evidentiary packages across major regulators to lower transaction costs and timelines. One example of an efficiency-driving approach can be seen in the guiding principles for “predetermined change control plans for machine learning-enabled medical devices” jointly published by the FDA, Health Canada, and the U.K.’s Medicines and Healthcare Products Regulatory Agency (MHRA) [^55].
- *Align incentives with demonstrated value*: develop reimbursement and coverage approaches that reflect incremental clinical value when biomarker-guided strategies improve outcomes, efficiency, or patient experience.

Taken together, these near-term steps and longer-term system needs can strengthen the evidence base and implementation pathway for digital biomarkers. Digital biomarkers have the potential to contribute to more efficient clinical trials, accellerate the development of new therapeutics, and, in selected contexts, more individualized care. This is predicated on rigorous fit-for-purpose validation, clearer regulatory expectations, and equity- and privacy-aware governance. The following priorities have been identified for the forthcoming years: targeted methodological research, improved regulatory convergence, and transparent, ethically grounded deployment.

## References

## Acknowledgements

A.D. Stern is a Research Fellow of the International Collaborative Bioscience Innovation and Law Programme (Inter-CeBIL programme), which is supported by Novo Nordisk Foundation Grant NNF23SA0087056. M.M. is supported by Charité’s Rahel-Hirsch-Programm. This study received no direct funding from any source.

## Funding

Open Access funding enabled and organized by Projekt DEAL.

## Ethics declarations

### Competing interests

A.D.S. reports no competing interests related to this study. She received honoraria for lecturing, consulting, and travel expenses for attending meetings from BIOTRONIK, Roche Diagnostics, Catalent, and AstraZeneca outside of the scope of this work and is an Advisory Board Member of the Peterson Health Technology Institute but declares no non-financial competing interests. J.L., M.M. declare no financial or non-financial competing interests.

## Peer review

### Peer review information

*Communications Medicine* thanks the anonymous reviewers for their contribution to the peer review of this work.

## Additional information

**Publisher’s note** Springer Nature remains neutral with regard to jurisdictional claims in published maps and institutional affiliations.

## Supplementary information

## Rights and permissions

**Open Access** This article is licensed under a Creative Commons Attribution 4.0 International License, which permits use, sharing, adaptation, distribution and reproduction in any medium or format, as long as you give appropriate credit to the original author(s) and the source, provide a link to the Creative Commons licence, and indicate if changes were made. The images or other third party material in this article are included in the article’s Creative Commons licence, unless indicated otherwise in a credit line to the material. If material is not included in the article’s Creative Commons licence and your intended use is not permitted by statutory regulation or exceeds the permitted use, you will need to obtain permission directly from the copyright holder. To view a copy of this licence, visit [http://creativecommons.org/licenses/by/4.0/](http://creativecommons.org/licenses/by/4.0/).

[^1]: FDA-NIH Biomarker Working Group. *BEST* (*Biomarkers, EndpointS, and Other Tools*) (FDA-NIH, 2021).

[^2]: Babrak, L. M. et al. Traditional and digital biomarkers: two worlds apart? *Digit. Biomark.* **3**, 92–102 (2019).

[Article](https://doi.org/10.1159%2F000502000) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=32095769) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC7015353) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Traditional%20and%20digital%20biomarkers%3A%20two%20worlds%20apart%3F&journal=Digit.%20Biomark.&doi=10.1159%2F000502000&volume=3&pages=92-102&publication_year=2019&author=Babrak%2CLM)

[^3]: Alonso, A. K. M., Hirt, J., Woelfle, T., Janiaud, P. & Hemkens, L. G. Definitions of digital biomarkers: a systematic mapping of the biomedical literature. *BMJ Health Care Inform.* **31**, e100914 (2024).

[Article](https://doi.org/10.1136%2Fbmjhci-2023-100914) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Definitions%20of%20digital%20biomarkers%3A%20a%20systematic%20mapping%20of%20the%20biomedical%20literature&journal=BMJ%20Health%20Care%20Inform.&doi=10.1136%2Fbmjhci-2023-100914&volume=31&publication_year=2024&author=Alonso%2CAKM&author=Hirt%2CJ&author=Woelfle%2CT&author=Janiaud%2CP&author=Hemkens%2CLG)

[^4]: Vasudevan, S., Saha, A., Tarver, M. E. & Patel, B. Digital biomarkers: convergence of digital health technologies and biomarkers. *NPJ Digit. Med.* **5**, 1–3 (2022).

[Article](https://doi.org/10.1038%2Fs41746-022-00583-z) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Digital%20biomarkers%3A%20convergence%20of%20digital%20health%20technologies%20and%20biomarkers&journal=NPJ%20Digit.%20Med.&doi=10.1038%2Fs41746-022-00583-z&volume=5&pages=1-3&publication_year=2022&author=Vasudevan%2CS&author=Saha%2CA&author=Tarver%2CME&author=Patel%2CB)

[^5]: Goldsack, J. C. et al. Verification, analytical validation, and clinical validation (V3): the foundation of determining fit-for-purpose for biometric monitoring technologies (BioMeTs). *NPJ Digit. Med.* **3**, 1–15 (2020).

[Article](https://doi.org/10.1038%2Fs41746-020-0260-4) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Verification%2C%20analytical%20validation%2C%20and%20clinical%20validation%20%28V3%29%3A%20the%20foundation%20of%20determining%20fit-for-purpose%20for%20biometric%20monitoring%20technologies%20%28BioMeTs%29&journal=NPJ%20Digit.%20Med.&doi=10.1038%2Fs41746-020-0260-4&volume=3&pages=1-15&publication_year=2020&author=Goldsack%2CJC)

[^6]: European Medicines Agency. Questions and answers: Qualification of digital technology-based methodologies to support approval of medicinal products. EMA/219860/2020 (European Medicines Agency, 2020). Accessed 11 Feb 2025. [https://www.ema.europa.eu/en/documents/other/questions-and-answers-qualification-digital-technology-based-methodologies-support-approval-medicinal-products\_en.pdf](https://www.ema.europa.eu/en/documents/other/questions-and-answers-qualification-digital-technology-based-methodologies-support-approval-medicinal-products_en.pdf)

[^7]: *Council Conclusions on Personalized Medicine for Patients* [https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=OJ:C:2015:421:FULL](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=OJ:C:2015:421:FULL) (2015).

[^8]: Landeck, L., Kneip, C., Reischl, J. & Asadullah, K. Biomarkers and personalized medicine: current status and further perspectives with special focus on dermatology. *Exp. Dermatol.* **25**, 333–339 (2016).

[Article](https://doi.org/10.1111%2Fexd.12948) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=27167702) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Biomarkers%20and%20personalized%20medicine%3A%20current%20status%20and%20further%20perspectives%20with%20special%20focus%20on%20dermatology&journal=Exp.%20Dermatol.&doi=10.1111%2Fexd.12948&volume=25&pages=333-339&publication_year=2016&author=Landeck%2CL&author=Kneip%2CC&author=Reischl%2CJ&author=Asadullah%2CK)

[^9]: Meister, S., Deiters, W. & Becker, S. Digital health and digital biomarkers–enabling value chains on health data. *Curr. Dir. Biomed. Eng.* **2**, 577–581 (2016).

[Article](https://doi.org/10.1515%2Fcdbme-2016-0128) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Digital%20health%20and%20digital%20biomarkers%E2%80%93enabling%20value%20chains%20on%20health%20data&journal=Curr.%20Dir.%20Biomed.%20Eng.&doi=10.1515%2Fcdbme-2016-0128&volume=2&pages=577-581&publication_year=2016&author=Meister%2CS&author=Deiters%2CW&author=Becker%2CS)

[^10]: Mandrola, J. & Foy, A. Downsides of detecting atrial fibrillation in asymptomatic patients. *Am. Fam. Physician* **99**, 354–355 (2019).

[PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=30874403) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Downsides%20of%20detecting%20atrial%20fibrillation%20in%20asymptomatic%20patients&journal=Am.%20Fam.%20Physician&volume=99&pages=354-355&publication_year=2019&author=Mandrola%2CJ&author=Foy%2CA)

[^11]: Burgess, S. W., Wilson, S. S. I., Cooper, D. M., Sly, P. D. & Devadason, S. G. In vitro evaluation of an asthma dosing device: the smart-inhaler. *Respir. Med.* **100**, 841–845 (2006).

[Article](https://doi.org/10.1016%2Fj.rmed.2005.09.004) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=16216485) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=In%20vitro%20evaluation%20of%20an%20asthma%20dosing%20device%3A%20the%20smart-inhaler&journal=Respir.%20Med.&doi=10.1016%2Fj.rmed.2005.09.004&volume=100&pages=841-845&publication_year=2006&author=Burgess%2CSW&author=Wilson%2CSSI&author=Cooper%2CDM&author=Sly%2CPD&author=Devadason%2CSG)

[^12]: Jansen, E. M. et al. Global burden of medication non-adherence in chronic obstructive pulmonary disease (COPD) and asthma: a narrative review of the clinical and economic case for smart inhalers. *J. Thorac. Dis.* **13**, 3846 (2021).

[Article](https://doi.org/10.21037%2Fjtd-20-2360) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=34277075) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC8264677) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Global%20burden%20of%20medication%20non-adherence%20in%20chronic%20obstructive%20pulmonary%20disease%20%28COPD%29%20and%20asthma%3A%20a%20narrative%20review%20of%20the%20clinical%20and%20economic%20case%20for%20smart%20inhalers&journal=J.%20Thorac.%20Dis.&doi=10.21037%2Fjtd-20-2360&volume=13&publication_year=2021&author=Jansen%2CEM)

[^13]: Gupta, S., Chang, P., Anyigbo, N. & Sabharwal, A. MobileSpiro: accurate mobile spirometry for self-management of asthma. In *Proc. First ACM Workshop on Mobile Systems, Applications, and Services for Healthcare* 1–6 (Association for Computing Machinery, 2011).

[^14]: Nathan, V., Vatanparvar, K., Rahman, M. M., Nemati, E. & Kuang, J. Assessment of chronic pulmonary disease patients using biomarkers from natural speech recorded by mobile devices. In *Proc. 2019 IEEE 16th International Conference on Wearable and Implantable Body Sensor Networks (BSN)* 1–4 (IEEE, 2019).

[^15]: Rodbard, D. Continuous glucose monitoring: a review of successes, challenges, and opportunities. *Diabetes Technol. Ther.* **18**, S2–S3 (2016).

[Article](https://doi.org/10.1089%2Fdia.2015.0417) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC28XhtlWrurs%3D) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Continuous%20glucose%20monitoring%3A%20a%20review%20of%20successes%2C%20challenges%2C%20and%20opportunities&journal=Diabetes%20Technol.%20Ther.&doi=10.1089%2Fdia.2015.0417&volume=18&pages=S2-S3&publication_year=2016&author=Rodbard%2CD)

[^16]: Battelino, T. et al. Continuous glucose monitoring and metrics for clinical trials: an international consensus statement. *Lancet Diabetes Endocrinol.* **11**, 42–57 (2023).

[Article](https://doi.org/10.1016%2FS2213-8587%2822%2900319-9) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BB38XjtVylsLnI) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=36493795) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Continuous%20glucose%20monitoring%20and%20metrics%20for%20clinical%20trials%3A%20an%20international%20consensus%20statement&journal=Lancet%20Diabetes%20Endocrinol.&doi=10.1016%2FS2213-8587%2822%2900319-9&volume=11&pages=42-57&publication_year=2023&author=Battelino%2CT)

[^17]: Maor, E. et al. Vocal biomarker is associated with hospitalization and mortality among heart failure patients. *J. Am. Heart Assoc.* **9**, e013359 (2020).

[Article](https://doi.org/10.1161%2FJAHA.119.013359) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=32233754) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC7428646) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Vocal%20biomarker%20is%20associated%20with%20hospitalization%20and%20mortality%20among%20heart%20failure%20patients&journal=J.%20Am.%20Heart%20Assoc.&doi=10.1161%2FJAHA.119.013359&volume=9&publication_year=2020&author=Maor%2CE)

[^18]: Truong, A. T. L. et al. CURATE.AI-assisted dose titration for anti-hypertensive personalized therapy: study protocol for a multi-arm, randomized, pilot feasibility trial using CURATE.AI (CURATE.AI ADAPT trial). *Eur. Heart J. Digit. Health* **5**, 41–49 (2024).

[Article](https://doi.org/10.1093%2Fehjdh%2Fztad063) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=38264697) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=CURATE.AI-assisted%20dose%20titration%20for%20anti-hypertensive%20personalized%20therapy%3A%20study%20protocol%20for%20a%20multi-arm%2C%20randomized%2C%20pilot%20feasibility%20trial%20using%20CURATE.AI%20%28CURATE.AI%20ADAPT%20trial%29&journal=Eur.%20Heart%20J.%20Digit.%20Health&doi=10.1093%2Fehjdh%2Fztad063&volume=5&pages=41-49&publication_year=2024&author=Truong%2CATL)

[^19]: Amir, O. et al. Evaluation of remote dielectric sensing (ReDS) technology-guided therapy for decreasing heart failure re-hospitalizations. *Int. J. Cardiol.* **240**, 279–284 (2017).

[Article](https://doi.org/10.1016%2Fj.ijcard.2017.02.120) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=28341372) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Evaluation%20of%20remote%20dielectric%20sensing%20%28ReDS%29%20technology-guided%20therapy%20for%20decreasing%20heart%20failure%20re-hospitalizations&journal=Int.%20J.%20Cardiol.&doi=10.1016%2Fj.ijcard.2017.02.120&volume=240&pages=279-284&publication_year=2017&author=Amir%2CO)

[^20]: Wong, C. K. et al. Daily ambulatory remote monitoring system for drug escalation in chronic heart failure with reduced ejection fraction: pilot phase of DAVID-HF study. *Eur. Heart J. Digit. Health* **3**, 284–295 (2022).

[Article](https://doi.org/10.1093%2Fehjdh%2Fztac024) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=36713022) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC9708020) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Daily%20ambulatory%20remote%20monitoring%20system%20for%20drug%20escalation%20in%20chronic%20heart%20failure%20with%20reduced%20ejection%20fraction%3A%20pilot%20phase%20of%20DAVID-HF%20study&journal=Eur.%20Heart%20J.%20Digit.%20Health&doi=10.1093%2Fehjdh%2Fztac024&volume=3&pages=284-295&publication_year=2022&author=Wong%2CCK)

[^21]: Low, D. M., Bentley, K. H. & Ghosh, S. S. Automated assessment of psychiatric disorders using speech: a systematic review. *Laryngoscope Investig. Otolaryngol.* **5**, 96–116 (2020).

[Article](https://doi.org/10.1002%2Flio2.354) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=32128436) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC7042657) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Automated%20assessment%20of%20psychiatric%20disorders%20using%20speech%3A%20a%20systematic%20review&journal=Laryngoscope%20Investig.%20Otolaryngol.&doi=10.1002%2Flio2.354&volume=5&pages=96-116&publication_year=2020&author=Low%2CDM&author=Bentley%2CKH&author=Ghosh%2CSS)

[^22]: Digital Medicine Society (DiMe) Library of Digital Endpoints. *Digital Medicine Society* *(DiMe)* [https://dimesociety.org/communication-education/library-of-digital-endpoints/](https://dimesociety.org/communication-education/library-of-digital-endpoints/)

[^23]: Scannell, J. W., Blanckley, A., Boldon, H. & Warrington, B. Diagnosing the decline in pharmaceutical R&D efficiency. *Nat. Rev. Drug Discov.* **11**, 191–200 (2012).

[Article](https://doi.org/10.1038%2Fnrd3681) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC38XivFyhtrY%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=22378269) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Diagnosing%20the%20decline%20in%20pharmaceutical%20R%26D%20efficiency&journal=Nat.%20Rev.%20Drug%20Discov.&doi=10.1038%2Fnrd3681&volume=11&pages=191-200&publication_year=2012&author=Scannell%2CJW&author=Blanckley%2CA&author=Boldon%2CH&author=Warrington%2CB)

[^24]: Wouters, O. J., McKee, M. & Luyten, J. Estimated research and development investment needed to bring a new medicine to market, 2009-2018. *JAMA* **323**, 844–853 (2020).

[Article](https://doi.org/10.1001%2Fjama.2020.1166) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=32125404) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC7054832) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Estimated%20research%20and%20development%20investment%20needed%20to%20bring%20a%20new%20medicine%20to%20market%2C%202009-2018&journal=JAMA&doi=10.1001%2Fjama.2020.1166&volume=323&pages=844-853&publication_year=2020&author=Wouters%2COJ&author=McKee%2CM&author=Luyten%2CJ)

[^25]: Harrison, R. K. Phase II and phase III failures: 2013–2015. *Nat. Rev. Drug Discov.* **15**, 817–818 (2016).

[Article](https://doi.org/10.1038%2Fnrd.2016.184) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC28XhslynsLvN) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=27811931) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Phase%20II%20and%20phase%20III%20failures%3A%202013%E2%80%932015&journal=Nat.%20Rev.%20Drug%20Discov.&doi=10.1038%2Fnrd.2016.184&volume=15&pages=817-818&publication_year=2016&author=Harrison%2CRK)

[^26]: Wu, S. S. et al. Reviving an R&D pipeline: a step change in the phase II success rate. *Drug Discov. Today* **26**, 308–314 (2021).

[Article](https://doi.org/10.1016%2Fj.drudis.2020.10.019) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BB38Xotlyntbk%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=33129994) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Reviving%20an%20R%26D%20pipeline%3A%20a%20step%20change%20in%20the%20phase%20II%20success%20rate&journal=Drug%20Discov.%20Today&doi=10.1016%2Fj.drudis.2020.10.019&volume=26&pages=308-314&publication_year=2021&author=Wu%2CSS)

[^27]: Servais, L. et al. First regulatory qualification of a novel digital endpoint in Duchenne muscular dystrophy: a multi-stakeholder perspective on the impact for patients and for drug development in neuromuscular diseases. *Digit. Biomark.* **5**, 183–190 (2021).

[Article](https://doi.org/10.1159%2F000517411) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=34723071) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC8460979) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=First%20regulatory%20qualification%20of%20a%20novel%20digital%20endpoint%20in%20Duchenne%20muscular%20dystrophy%3A%20a%20multi-stakeholder%20perspective%20on%20the%20impact%20for%20patients%20and%20for%20drug%20development%20in%20neuromuscular%20diseases&journal=Digit.%20Biomark.&doi=10.1159%2F000517411&volume=5&pages=183-190&publication_year=2021&author=Servais%2CL)

[^28]: Mori, H., Wiklund, S. J. & Zhang, J. Y. Quantifying the benefits of digital biomarkers and technology-based study endpoints in clinical trials: Project Moneyball. *Digit. Biomark.* **6**, 36–46 (2022).

[Article](https://doi.org/10.1159%2F000525255) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=35949224) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC9297703) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Quantifying%20the%20benefits%20of%20digital%20biomarkers%20and%20technology-based%20study%20endpoints%20in%20clinical%20trials%3A%20Project%20Moneyball&journal=Digit.%20Biomark.&doi=10.1159%2F000525255&volume=6&pages=36-46&publication_year=2022&author=Mori%2CH&author=Wiklund%2CSJ&author=Zhang%2CJY)

[^29]: Chen, C. et al. Wrist-worn sensor-based measurements for drug effect detection with small samples in people with Lewy body dementia. *Park. Relat. Disord.* **109**, 105355 (2023).

[Article](https://doi.org/10.1016%2Fj.parkreldis.2023.105355) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BB3sXlslymu7o%3D) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Wrist-worn%20sensor-based%20measurements%20for%20drug%20effect%20detection%20with%20small%20samples%20in%20people%20with%20Lewy%20body%20dementia&journal=Park.%20Relat.%20Disord.&doi=10.1016%2Fj.parkreldis.2023.105355&volume=109&publication_year=2023&author=Chen%2CC)

[^30]: Leptak, C. et al. What evidence do we need for biomarker qualification? *Sci. Transl. Med.* **9**, eaal4599 (2017).

[Article](https://doi.org/10.1126%2Fscitranslmed.aal4599) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=29167393) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=What%20evidence%20do%20we%20need%20for%20biomarker%20qualification%3F&journal=Sci.%20Transl.%20Med.&doi=10.1126%2Fscitranslmed.aal4599&volume=9&publication_year=2017&author=Leptak%2CC)

[^31]: Krieger, J. L. Trials and terminations: learning from competitors’ R&D failures. *Manag. Sci.* **67**, 5525–5548 (2021).

[Article](https://doi.org/10.1287%2Fmnsc.2020.3775) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Trials%20and%20terminations%3A%20learning%20from%20competitors%E2%80%99%20R%26D%20failures&journal=Manag.%20Sci.&doi=10.1287%2Fmnsc.2020.3775&volume=67&pages=5525-5548&publication_year=2021&author=Krieger%2CJL)

[^32]: DiMasi, J. A. et al. Assessing the net financial benefits of employing digital endpoints in clinical trials. *Clin. Transl. Sci.* **17**, e13902 (2024).

[Article](https://doi.org/10.1111%2Fcts.13902) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=39072949) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC11284240) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Assessing%20the%20net%20financial%20benefits%20of%20employing%20digital%20endpoints%20in%20clinical%20trials&journal=Clin.%20Transl.%20Sci.&doi=10.1111%2Fcts.13902&volume=17&publication_year=2024&author=DiMasi%2CJA)

[^33]: Dodge, H. H. et al. Use of high-frequency in-home monitoring data may reduce sample sizes needed in clinical trials. *PLoS ONE* **10**, e0138095 (2015).

[Article](https://doi.org/10.1371%2Fjournal.pone.0138095) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=26379170) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4574479) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Use%20of%20high-frequency%20in-home%20monitoring%20data%20may%20reduce%20sample%20sizes%20needed%20in%20clinical%20trials&journal=PLoS%20ONE&doi=10.1371%2Fjournal.pone.0138095&volume=10&publication_year=2015&author=Dodge%2CHH)

[^34]: Mittermaier, M., Venkatesh, K. P. & Kvedar, J. C. Digital health technology in clinical trials. *NPJ Digit. Med.* **6**, 88 (2023).

[Article](https://doi.org/10.1038%2Fs41746-023-00841-8) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=37202443) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC10195788) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Digital%20health%20technology%20in%20clinical%20trials&journal=NPJ%20Digit.%20Med.&doi=10.1038%2Fs41746-023-00841-8&volume=6&publication_year=2023&author=Mittermaier%2CM&author=Venkatesh%2CKP&author=Kvedar%2CJC)

[^35]: Insel, T. R. Digital phenotyping: technology for a new science of behavior. *JAMA* **318**, 1215 (2017).

[Article](https://doi.org/10.1001%2Fjama.2017.11295) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=28973224) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Digital%20phenotyping%3A%20technology%20for%20a%20new%20science%20of%20behavior&journal=JAMA&doi=10.1001%2Fjama.2017.11295&volume=318&publication_year=2017&author=Insel%2CTR)

[^36]: Coravos, A. et al. Digital medicine: a primer on measurement. *Digit. Biomark.* **3**, 31–71 (2019).

[Article](https://doi.org/10.1159%2F000500413) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=32095767) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC7015383) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Digital%20medicine%3A%20a%20primer%20on%20measurement&journal=Digit.%20Biomark.&doi=10.1159%2F000500413&volume=3&pages=31-71&publication_year=2019&author=Coravos%2CA)

[^37]: Poste, G. Bring on the biomarkers. *Nature* **469**, 156–157 (2011).

[Article](https://doi.org/10.1038%2F469156a) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC3MXkvFejsw%3D%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=21228852) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Bring%20on%20the%20biomarkers&journal=Nature&doi=10.1038%2F469156a&volume=469&pages=156-157&publication_year=2011&author=Poste%2CG)

[^38]: Lavezzari, G. & Womack, A. W. Industry perspectives on biomarker qualification. *Clin. Pharmacol. Ther.* **99**, 208–213 (2016).

[Article](https://doi.org/10.1002%2Fcpt.264) [CAS](https://www.nature.com/articles/cas-redirect/1:STN:280:DC%2BC283jtV2mtg%3D%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=26378777) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Industry%20perspectives%20on%20biomarker%20qualification&journal=Clin.%20Pharmacol.%20Ther.&doi=10.1002%2Fcpt.264&volume=99&pages=208-213&publication_year=2016&author=Lavezzari%2CG&author=Womack%2CAW)

[^39]: U.S. Food and Drug Administration, Center for Drug Evaluation and Research (CDER) & Center for Biologics Evaluation and Research (CBER). Qualification Process for Drug Development Tools: Guidance for Industry and FDA Staff. (FDA, Nov 2020). Accessed 11 Feb 2025. [https://www.fda.gov/media/133511/download](https://www.fda.gov/media/133511/download)

[^40]: U.S. Food and Drug Administration, Center for Drug Evaluation and Research (CDER), CDER COA Qualification Program (CDER COAQP). COAQP Information Session. (FDA, n.d.). Accessed 11 Feb 2025. [https://www.fda.gov/media/151216/download](https://www.fda.gov/media/151216/download)

[^41]: Shahzad, M. & Stern, A. D. Participants in the FDA’s biomarker qualification program. *Clin. Pharmacol. Ther*. [https://doi.org/10.1002/cpt.3661](https://doi.org/10.1002/cpt.3661) (2025).

[^42]: Manta, C., Patrick-Lake, B. & Goldsack, J. C. Digital measures that matter to patients: a framework to guide the selection and development of digital measures of health. *Digit. Biomark.* **4**, 69–77 (2020).

[Article](https://doi.org/10.1159%2F000509725) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=33083687) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC7548919) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Digital%20measures%20that%20matter%20to%20patients%3A%20a%20framework%20to%20guide%20the%20selection%20and%20development%20of%20digital%20measures%20of%20health&journal=Digit.%20Biomark.&doi=10.1159%2F000509725&volume=4&pages=69-77&publication_year=2020&author=Manta%2CC&author=Patrick-Lake%2CB&author=Goldsack%2CJC)

[^43]: Shah, S. J., Eckman, M. H., Aspberg, S., Go, A. S. & Singer, D. E. Effect of variation in published stroke rates on the net clinical benefit of anticoagulation for atrial fibrillation. *Ann. Intern. Med.* **169**, 517–527 (2018).

[Article](https://doi.org/10.7326%2FM17-2762) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=30264130) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Effect%20of%20variation%20in%20published%20stroke%20rates%20on%20the%20net%20clinical%20benefit%20of%20anticoagulation%20for%20atrial%20fibrillation&journal=Ann.%20Intern.%20Med.&doi=10.7326%2FM17-2762&volume=169&pages=517-527&publication_year=2018&author=Shah%2CSJ&author=Eckman%2CMH&author=Aspberg%2CS&author=Go%2CAS&author=Singer%2CDE)

[^44]: Gibson, C. M. et al. Does early detection of atrial fibrillation reduce the risk of thromboembolic events? Rationale and design of the Heartline study. *Am. Heart J.* **259**, 30–41 (2023).

[Article](https://doi.org/10.1016%2Fj.ahj.2023.01.004) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=36642226) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Does%20early%20detection%20of%20atrial%20fibrillation%20reduce%20the%20risk%20of%20thromboembolic%20events%3F%20Rationale%20and%20design%20of%20the%20Heartline%20study&journal=Am.%20Heart%20J.&doi=10.1016%2Fj.ahj.2023.01.004&volume=259&pages=30-41&publication_year=2023&author=Gibson%2CCM)

[^45]: Nagappan, A., Krasniansky, A. & Knowles, M. Patterns of ownership and usage of wearable devices in the United States, 2020-2022: survey study. *J. Med. Internet Res.* **26**, e56504 (2024).

[Article](https://doi.org/10.2196%2F56504) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=39058548) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC11316147) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Patterns%20of%20ownership%20and%20usage%20of%20wearable%20devices%20in%20the%20United%20States%2C%202020-2022%3A%20survey%20study&journal=J.%20Med.%20Internet%20Res.&doi=10.2196%2F56504&volume=26&publication_year=2024&author=Nagappan%2CA&author=Krasniansky%2CA&author=Knowles%2CM)

[^46]: Obermeyer, Z., Powers, B., Vogeli, C. & Mullainathan, S. Dissecting racial bias in an algorithm used to manage the health of populations. *Science* **366**, 447–453 (2019).

[Article](https://doi.org/10.1126%2Fscience.aax2342) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC1MXitVemtrjF) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31649194) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Dissecting%20racial%20bias%20in%20an%20algorithm%20used%20to%20manage%20the%20health%20of%20populations&journal=Science&doi=10.1126%2Fscience.aax2342&volume=366&pages=447-453&publication_year=2019&author=Obermeyer%2CZ&author=Powers%2CB&author=Vogeli%2CC&author=Mullainathan%2CS)

[^47]: Guo, L. N., Lee, M. S., Kassamali, B., Mita, C. & Nambudiri, V. E. Bias in, bias out: underreporting and underrepresentation of diverse skin types in machine learning research for skin cancer detection—a scoping review. *J. Am. Acad. Dermatol.* **87**, 157–159 (2022).

[Article](https://doi.org/10.1016%2Fj.jaad.2021.06.884) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=34252465) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Bias%20in%2C%20bias%20out%3A%20underreporting%20and%20underrepresentation%20of%20diverse%20skin%20types%20in%20machine%20learning%20research%20for%20skin%20cancer%20detection%E2%80%94a%20scoping%20review&journal=J.%20Am.%20Acad.%20Dermatol.&doi=10.1016%2Fj.jaad.2021.06.884&volume=87&pages=157-159&publication_year=2022&author=Guo%2CLN&author=Lee%2CMS&author=Kassamali%2CB&author=Mita%2CC&author=Nambudiri%2CVE)

[^48]: Stern, A. D., Alexander, B. M. & Chandra, A. Innovation incentives and biomarkers. *Clin. Pharmacol. Ther.* **103**, 34–36 (2018).

[Article](https://doi.org/10.1002%2Fcpt.876) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC2sXitVCrsL%2FF) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=29034452) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Innovation%20incentives%20and%20biomarkers&journal=Clin.%20Pharmacol.%20Ther.&doi=10.1002%2Fcpt.876&volume=103&pages=34-36&publication_year=2018&author=Stern%2CAD&author=Alexander%2CBM&author=Chandra%2CA)

[^49]: Brekke, K. R., Dalen, D. M. & Straume, O. R. Competing with precision: incentives for developing predictive biomarker tests. *Scand. J. Econ.* **126**, 60–97 (2024).

[Article](https://doi.org/10.1111%2Fsjoe.12543) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Competing%20with%20precision%3A%20incentives%20for%20developing%20predictive%20biomarker%20tests&journal=Scand.%20J.%20Econ.&doi=10.1111%2Fsjoe.12543&volume=126&pages=60-97&publication_year=2024&author=Brekke%2CKR&author=Dalen%2CDM&author=Straume%2COR)

[^50]: Antoñanzas, F., Juárez-Castelló, C. A. & Rodríguez-Ibeas, R. Pre-approval incentives to promote adoption of personalized medicine: a theoretical approach. *Health Econ. Rev.* **9**, 28 (2019).

[Article](https://link.springer.com/doi/10.1186/s13561-019-0244-8) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31664604) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6820936) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Pre-approval%20incentives%20to%20promote%20adoption%20of%20personalized%20medicine%3A%20a%20theoretical%20approach&journal=Health%20Econ.%20Rev.&doi=10.1186%2Fs13561-019-0244-8&volume=9&publication_year=2019&author=Anto%C3%B1anzas%2CF&author=Ju%C3%A1rez-Castell%C3%B3%2CCA&author=Rodr%C3%ADguez-Ibeas%2CR)

[^51]: Torous, J., Kiang, M. V., Lorme, J. & Onnela, J.-P. New tools for new research in psychiatry: a scalable and customizable platform to empower data driven smartphone research. *JMIR Ment. Health* **3**, e5165 (2016).

[Article](https://doi.org/10.2196%2Fmental.5165) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=New%20tools%20for%20new%20research%20in%20psychiatry%3A%20a%20scalable%20and%20customizable%20platform%20to%20empower%20data%20driven%20smartphone%20research&journal=JMIR%20Ment.%20Health&doi=10.2196%2Fmental.5165&volume=3&publication_year=2016&author=Torous%2CJ&author=Kiang%2CMV&author=Lorme%2CJ&author=Onnela%2CJ-P)

[^52]: Coorey, G. et al. The health digital twin to tackle cardiovascular disease—a review of an emerging interdisciplinary field. *NPJ Digit. Med.* **5**, 1–12 (2022).

[Article](https://doi.org/10.1038%2Fs41746-022-00640-7) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20health%20digital%20twin%20to%20tackle%20cardiovascular%20disease%E2%80%94a%20review%20of%20an%20emerging%20interdisciplinary%20field&journal=NPJ%20Digit.%20Med.&doi=10.1038%2Fs41746-022-00640-7&volume=5&pages=1-12&publication_year=2022&author=Coorey%2CG)

[^53]: FDA. FDA Announces Plan to Phase Out Animal Testing Requirement for Monoclonal Antibodies and Other Drugs. *FDA* [https://www.fda.gov/news-events/press-announcements/fda-announces-plan-phase-out-animal-testing-requirement-monoclonal-antibodies-and-other-drugs](https://www.fda.gov/news-events/press-announcements/fda-announces-plan-phase-out-animal-testing-requirement-monoclonal-antibodies-and-other-drugs) (2025).

[^54]: PitchBook, D. PitchBook. *Venture Capital*, *Private Equity and M&A Database* [https://pitchbook.com/](https://pitchbook.com/)

[^55]: FDA. Predetermined Change Control Plans for Machine Learning-Enabled Medical Devices: Guiding Principles. [https://www.fda.gov/medical-devices/software-medical-device-samd/predetermined-change-control-plans-machine-learning-enabled-medical-devices-guiding-principles](https://www.fda.gov/medical-devices/software-medical-device-samd/predetermined-change-control-plans-machine-learning-enabled-medical-devices-guiding-principles) (2025).

[^56]: Tison, G. H. et al. Passive detection of atrial fibrillation using a commercially available smartwatch. *JAMA Cardiol* **3**, 409–416 (2018).

[Article](https://doi.org/10.1001%2Fjamacardio.2018.0136) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=29562087) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC5875390) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Passive%20detection%20of%20atrial%20fibrillation%20using%20a%20commercially%20available%20smartwatch&journal=JAMA%20Cardiol&doi=10.1001%2Fjamacardio.2018.0136&volume=3&pages=409-416&publication_year=2018&author=Tison%2CGH)

[^57]: Perez, M. V. et al. Large-scale assessment of a smartwatch to identify atrial fibrillation. *N. Engl. J. Med.* **381**, 1909–1917 (2019).

[Article](https://doi.org/10.1056%2FNEJMoa1901183) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31722151) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC8112605) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Large-scale%20assessment%20of%20a%20smartwatch%20to%20identify%20atrial%20fibrillation&journal=N.%20Engl.%20J.%20Med.&doi=10.1056%2FNEJMoa1901183&volume=381&pages=1909-1917&publication_year=2019&author=Perez%2CMV)

[^58]: Rusz, J. et al. Smartphone allows capture of speech abnormalities associated with high risk of developing Parkinson’s disease. *IEEE Trans. Neural Syst. Rehabil. Eng.* **26**, 1495–1507 (2018).

[Article](https://doi.org/10.1109%2FTNSRE.2018.2851787) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=29994713) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Smartphone%20allows%20capture%20of%20speech%20abnormalities%20associated%20with%20high%20risk%20of%20developing%20Parkinson%E2%80%99s%20disease&journal=IEEE%20Trans.%20Neural%20Syst.%20Rehabil.%20Eng.&doi=10.1109%2FTNSRE.2018.2851787&volume=26&pages=1495-1507&publication_year=2018&author=Rusz%2CJ)

[^59]: Wroge, T. J. et al. Parkinson’s disease diagnosis using machine learning and voice. In *Proc. 2018 IEEE Signal Processing in Medicine and Biology Symposium (SPMB)* 1–7 (IEEE, 2018).

[^60]: Karaman, O., Çakın, H., Alhudhaif, A. & Polat, K. Robust automated Parkinson disease detection based on voice signals with transfer learning. *Expert Syst. Appl.* **178**, 115013 (2021).

[Article](https://doi.org/10.1016%2Fj.eswa.2021.115013) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Robust%20automated%20Parkinson%20disease%20detection%20based%20on%20voice%20signals%20with%20transfer%20learning&journal=Expert%20Syst.%20Appl.&doi=10.1016%2Fj.eswa.2021.115013&volume=178&publication_year=2021&author=Karaman%2CO&author=%C3%87ak%C4%B1n%2CH&author=Alhudhaif%2CA&author=Polat%2CK)

[^61]: Laganas, C. et al. Parkinson’s disease detection based on running speech data from phone calls. *IEEE Trans. Biomed. Eng.* **69**, 1573–1584 (2022).

[Article](https://doi.org/10.1109%2FTBME.2021.3116935) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=34596531) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Parkinson%E2%80%99s%20disease%20detection%20based%20on%20running%20speech%20data%20from%20phone%20calls&journal=IEEE%20Trans.%20Biomed.%20Eng.&doi=10.1109%2FTBME.2021.3116935&volume=69&pages=1573-1584&publication_year=2022&author=Laganas%2CC)

[^62]: Georgiou, K. et al. Can wearable devices accurately measure heart rate variability? A systematic review. *Folia Med.* **60**, 7–20 (2018).

[^63]: Sana, F. et al. Wearable devices for ambulatory cardiac monitoring. *J. Am. Coll. Cardiol.* **75**, 1582–1592 (2020).

[Article](https://doi.org/10.1016%2Fj.jacc.2020.01.046) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=32241375) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC7316129) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Wearable%20devices%20for%20ambulatory%20cardiac%20monitoring&journal=J.%20Am.%20Coll.%20Cardiol.&doi=10.1016%2Fj.jacc.2020.01.046&volume=75&pages=1582-1592&publication_year=2020&author=Sana%2CF)

[^64]: Kuwabara, M., Harada, K., Hishiki, Y. & Kario, K. Validation of two watch-type wearable blood pressure monitors according to the ANSI/AAMI/ISO81060-2:2013 guidelines: Omron HEM-6410T-ZM and HEM-6410T-ZL. *J. Clin. Hypertens.* **21**, 853–858 (2019).

[Article](https://doi.org/10.1111%2Fjch.13499) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Validation%20of%20two%20watch-type%20wearable%20blood%20pressure%20monitors%20according%20to%20the%20ANSI%2FAAMI%2FISO81060-2%3A2013%20guidelines%3A%20Omron%20HEM-6410T-ZM%20and%20HEM-6410T-ZL&journal=J.%20Clin.%20Hypertens.&doi=10.1111%2Fjch.13499&volume=21&pages=853-858&publication_year=2019&author=Kuwabara%2CM&author=Harada%2CK&author=Hishiki%2CY&author=Kario%2CK)

[^65]: Duncker, D. et al. Smart wearables for cardiac monitoring—real-world use beyond atrial fibrillation. *Sensors* **21**, 2539 (2021).

[Article](https://doi.org/10.3390%2Fs21072539) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=33916371) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC8038592) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Smart%20wearables%20for%20cardiac%20monitoring%E2%80%94real-world%20use%20beyond%20atrial%20fibrillation&journal=Sensors&doi=10.3390%2Fs21072539&volume=21&publication_year=2021&author=Duncker%2CD)

[^66]: Gill, S. K. et al. Consumer wearable devices for evaluation of heart rate control using digoxin versus beta-blockers: the RATE-AF randomized trial. *Nat. Med.* **30**, 2030–2036 (2024).

[Article](https://doi.org/10.1038%2Fs41591-024-03094-4) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BB2cXhsFGltbfN) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=39009776) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC11271403) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Consumer%20wearable%20devices%20for%20evaluation%20of%20heart%20rate%20control%20using%20digoxin%20versus%20beta-blockers%3A%20the%20RATE-AF%20randomized%20trial&journal=Nat.%20Med.&doi=10.1038%2Fs41591-024-03094-4&volume=30&pages=2030-2036&publication_year=2024&author=Gill%2CSK)

[^67]: Hernández, C. R. et al. Validation of the portable air-smart spirometer. *PLOS ONE* **13**, e0192789 (2018).

[Article](https://doi.org/10.1371%2Fjournal.pone.0192789) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Validation%20of%20the%20portable%20air-smart%20spirometer&journal=PLOS%20ONE&doi=10.1371%2Fjournal.pone.0192789&volume=13&publication_year=2018&author=Hern%C3%A1ndez%2CCR)

[^68]: Zhou, P., Yang, L. & Huang, Y.-X. A smart phone based handheld wireless spirometer with functions and precision comparable to laboratory spirometers. *Sensors* **19**, 2487 (2019).

[Article](https://doi.org/10.3390%2Fs19112487) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31159155) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6603793) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=A%20smart%20phone%20based%20handheld%20wireless%20spirometer%20with%20functions%20and%20precision%20comparable%20to%20laboratory%20spirometers&journal=Sensors&doi=10.3390%2Fs19112487&volume=19&publication_year=2019&author=Zhou%2CP&author=Yang%2CL&author=Huang%2CY-X)

[^69]: Rodbard, H. W. et al. The effect of canagliflozin, a sodium glucose cotransporter 2 inhibitor, on glycemic end points assessed by continuous glucose monitoring and patient-reported outcomes among people with type 1 diabetes. *Diabetes Care* **40**, 171–180 (2016).

[Article](https://doi.org/10.2337%2Fdc16-1353) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=27899497) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20effect%20of%20canagliflozin%2C%20a%20sodium%20glucose%20cotransporter%202%20inhibitor%2C%20on%20glycemic%20end%20points%20assessed%20by%20continuous%20glucose%20monitoring%20and%20patient-reported%20outcomes%20among%20people%20with%20type%201%20diabetes&journal=Diabetes%20Care&doi=10.2337%2Fdc16-1353&volume=40&pages=171-180&publication_year=2016&author=Rodbard%2CHW)

[^70]: Lawton, M. et al. Parkinson’s disease subtypes in the Oxford Parkinson disease centre (OPDC) discovery cohort. *J. Park. Dis.* **5**, 269–279 (2015).

[Google Scholar](http://scholar.google.com/scholar_lookup?&title=Parkinson%E2%80%99s%20disease%20subtypes%20in%20the%20Oxford%20Parkinson%20disease%20centre%20%28OPDC%29%20discovery%20cohort&journal=J.%20Park.%20Dis.&volume=5&pages=269-279&publication_year=2015&author=Lawton%2CM)

[^71]: Bloem, B. R. et al. The personalized Parkinson project: examining disease progression through broad biomarkers in early Parkinson’s disease. *BMC Neurol.* **19**, 160 (2019).

[Article](https://link.springer.com/doi/10.1186/s12883-019-1394-3) [CAS](https://www.nature.com/articles/cas-redirect/1:STN:280:DC%2BB3Mzotlejsw%3D%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31315608) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6636112) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20personalized%20Parkinson%20project%3A%20examining%20disease%20progression%20through%20broad%20biomarkers%20in%20early%20Parkinson%E2%80%99s%20disease&journal=BMC%20Neurol.&doi=10.1186%2Fs12883-019-1394-3&volume=19&publication_year=2019&author=Bloem%2CBR)

[^72]: Sturchio, A. et al. Phenotype-agnostic molecular subtyping of neurodegenerative disorders: the Cincinnati cohort biomarker program (CCBP). *Front. Aging Neurosci.* **12**, 553635 (2020).

[Article](https://doi.org/10.3389%2Ffnagi.2020.553635) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BB3MXisF2nsro%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=33132895) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC7578373) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Phenotype-agnostic%20molecular%20subtyping%20of%20neurodegenerative%20disorders%3A%20the%20Cincinnati%20cohort%20biomarker%20program%20%28CCBP%29&journal=Front.%20Aging%20Neurosci.&doi=10.3389%2Ffnagi.2020.553635&volume=12&publication_year=2020&author=Sturchio%2CA)

[^73]: Trebeschi, S. et al. Predicting response to cancer immunotherapy using noninvasive radiomic biomarkers. *Ann. Oncol.* **30**, 998–1004 (2019).

[Article](https://doi.org/10.1093%2Fannonc%2Fmdz108) [CAS](https://www.nature.com/articles/cas-redirect/1:STN:280:DC%2BB3cbmsFWntA%3D%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=30895304) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6594459) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Predicting%20response%20to%20cancer%20immunotherapy%20using%20noninvasive%20radiomic%20biomarkers&journal=Ann.%20Oncol.&doi=10.1093%2Fannonc%2Fmdz108&volume=30&pages=998-1004&publication_year=2019&author=Trebeschi%2CS)

[^74]: Johannet, P. et al. Using machine learning algorithms to predict immunotherapy response in patients with advanced melanoma. *Clin. Cancer Res.* **27**, 131–140 (2021).

[Article](https://doi.org/10.1158%2F1078-0432.CCR-20-2415) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BB3MXltlWjs7w%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=33208341) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Using%20machine%20learning%20algorithms%20to%20predict%20immunotherapy%20response%20in%20patients%20with%20advanced%20melanoma&journal=Clin.%20Cancer%20Res.&doi=10.1158%2F1078-0432.CCR-20-2415&volume=27&pages=131-140&publication_year=2021&author=Johannet%2CP)

[^75]: Kong, J. et al. Network-based machine learning approach to predict immunotherapy response in cancer patients. *Nat. Commun.* **13**, 3703 (2022).

[Article](https://doi.org/10.1038%2Fs41467-022-31535-6) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BB38XhslajsLrF) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=35764641) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC9240063) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Network-based%20machine%20learning%20approach%20to%20predict%20immunotherapy%20response%20in%20cancer%20patients&journal=Nat.%20Commun.&doi=10.1038%2Fs41467-022-31535-6&volume=13&publication_year=2022&author=Kong%2CJ)

[^76]: Noh, B. et al. XGBoost based machine learning approach to predict the risk of fall in older adults using gait outcomes. *Sci. Rep.* **11**, 12183 (2021).

[Article](https://doi.org/10.1038%2Fs41598-021-91797-w) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BB3MXhsFyitL7K) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=34108595) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC8190134) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=XGBoost%20based%20machine%20learning%20approach%20to%20predict%20the%20risk%20of%20fall%20in%20older%20adults%20using%20gait%20outcomes&journal=Sci.%20Rep.&doi=10.1038%2Fs41598-021-91797-w&volume=11&publication_year=2021&author=Noh%2CB)

[^77]: Connie, T. & Zhe Khae, L. Fall risk prediction using temporal gait features and machine learning approaches. *Front. Artif. Intell*. **7**, 1425713 (2024).

[^78]: Bonkhoff, A. K. & Grefkes, C. Precision medicine in stroke: towards personalized outcome predictions using artificial intelligence. *Brain* **145**, 457–475 (2022).

[Article](https://doi.org/10.1093%2Fbrain%2Fawab439) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=34918041) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC9014757) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Precision%20medicine%20in%20stroke%3A%20towards%20personalized%20outcome%20predictions%20using%20artificial%20intelligence&journal=Brain&doi=10.1093%2Fbrain%2Fawab439&volume=145&pages=457-475&publication_year=2022&author=Bonkhoff%2CAK&author=Grefkes%2CC)

[^79]: Mainali, S., Darsie, M. E. & Smetana, K. S. Machine learning in action: stroke diagnosis and outcome prediction. *Front. Neurol*. **12**, 734345 (2021).

[^80]: Cheon, S., Kim, J. & Lim, J. The use of deep learning to predict stroke patient mortality. *Int. J. Environ. Res. Public Health* **16**, 1876 (2019).

[Article](https://doi.org/10.3390%2Fijerph16111876) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31141892) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6603534) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20use%20of%20deep%20learning%20to%20predict%20stroke%20patient%20mortality&journal=Int.%20J.%20Environ.%20Res.%20Public%20Health&doi=10.3390%2Fijerph16111876&volume=16&publication_year=2019&author=Cheon%2CS&author=Kim%2CJ&author=Lim%2CJ)

[^81]: Castelletti, S. et al. A wearable remote monitoring system for the identification of subjects with a prolonged QT interval or at risk for drug-induced long QT syndrome. *Int. J. Cardiol.* **266**, 89–94 (2018).

[Article](https://doi.org/10.1016%2Fj.ijcard.2018.03.097) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=29887480) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=A%20wearable%20remote%20monitoring%20system%20for%20the%20identification%20of%20subjects%20with%20a%20prolonged%20QT%20interval%20or%20at%20risk%20for%20drug-induced%20long%20QT%20syndrome&journal=Int.%20J.%20Cardiol.&doi=10.1016%2Fj.ijcard.2018.03.097&volume=266&pages=89-94&publication_year=2018&author=Castelletti%2CS)

[^82]: Tsuji, H. et al. Impact of reduced heart rate variability on risk for cardiac events. *Circulation* **94**, 2850–2855 (1996).

[Article](https://doi.org/10.1161%2F01.CIR.94.11.2850) [CAS](https://www.nature.com/articles/cas-redirect/1:STN:280:DyaK2s%2Fps1Srug%3D%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=8941112) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Impact%20of%20reduced%20heart%20rate%20variability%20on%20risk%20for%20cardiac%20events&journal=Circulation&doi=10.1161%2F01.CIR.94.11.2850&volume=94&pages=2850-2855&publication_year=1996&author=Tsuji%2CH)

[^83]: Thayer, J. F., Yamamoto, S. S. & Brosschot, J. F. The relationship of autonomic imbalance, heart rate variability and cardiovascular disease risk factors. *Int. J. Cardiol.* **141**, 122–131 (2010).

[Article](https://doi.org/10.1016%2Fj.ijcard.2009.09.543) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=19910061) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20relationship%20of%20autonomic%20imbalance%2C%20heart%20rate%20variability%20and%20cardiovascular%20disease%20risk%20factors&journal=Int.%20J.%20Cardiol.&doi=10.1016%2Fj.ijcard.2009.09.543&volume=141&pages=122-131&publication_year=2010&author=Thayer%2CJF&author=Yamamoto%2CSS&author=Brosschot%2CJF)

[^84]: Huikuri, H. V. & Stein, P. K. Heart rate variability in risk stratification of cardiac patients. *Prog. Cardiovasc. Dis.* **56**, 153–159 (2013).

[Article](https://doi.org/10.1016%2Fj.pcad.2013.07.003) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=24215747) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Heart%20rate%20variability%20in%20risk%20stratification%20of%20cardiac%20patients&journal=Prog.%20Cardiovasc.%20Dis.&doi=10.1016%2Fj.pcad.2013.07.003&volume=56&pages=153-159&publication_year=2013&author=Huikuri%2CHV&author=Stein%2CPK)

[^85]: Zheng, N. S. et al. Sleep patterns and risk of chronic disease as measured by long-term monitoring with commercial wearable devices in the All of Us Research Program. *Nat. Med.* **30**, 2648–2656 (2024).

[Article](https://doi.org/10.1038%2Fs41591-024-03155-8) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BB2cXhs1ShsbjP) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=39030265) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC11405268) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Sleep%20patterns%20and%20risk%20of%20chronic%20disease%20as%20measured%20by%20long-term%20monitoring%20with%20commercial%20wearable%20devices%20in%20the%20All%20of%20Us%20Research%20Program&journal=Nat.%20Med.&doi=10.1038%2Fs41591-024-03155-8&volume=30&pages=2648-2656&publication_year=2024&author=Zheng%2CNS)

[^86]: Zhang, J. et al. Association of sleep duration and risk of mental disorder: a systematic review and meta-analysis. *Sleep Breath* **28**, 261–280 (2024).

[Article](https://link.springer.com/doi/10.1007/s11325-023-02905-1) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=37642884) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Association%20of%20sleep%20duration%20and%20risk%20of%20mental%20disorder%3A%20a%20systematic%20review%20and%20meta-analysis&journal=Sleep%20Breath&doi=10.1007%2Fs11325-023-02905-1&volume=28&pages=261-280&publication_year=2024&author=Zhang%2CJ)