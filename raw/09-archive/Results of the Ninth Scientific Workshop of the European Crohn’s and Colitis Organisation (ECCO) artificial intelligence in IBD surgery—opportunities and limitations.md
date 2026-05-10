---
title: "Results of the Ninth Scientific Workshop of the European Crohn’s and Colitis Organisation (ECCO): artificial intelligence in IBD surgery—opportunities and limitations"
source: "https://academic.oup.com/ecco-jcc/article/20/4/jjaf135/8232298?login=false"
author:
  - "[[Alaa El-Hussuna]]"
  - "[[Gianluca Pellino]]"
  - "[[Alessandra Soriano]]"
  - "[[Kapil Sahnan]]"
  - "[[Aart Mookhoek]]"
  - "[[Pieter Sinonquel]]"
  - "[[Mariangela Allocca]]"
  - "[[Dan Carter]]"
  - "[[Arzu Ensari]]"
  - "[[Marietta Iacucci]]"
  - "[[Uri Kopylov]]"
  - "[[Bram Verstockt]]"
  - "[[Daniel C Baumgart]]"
  - "[[Nurulamin M Noor]]"
  - "[[Urko M Marigorta]]"
  - "[[Daniele Noviello]]"
  - "[[Peter Bossuyt]]"
  - "[[Jan de Laffolie]]"
  - "[[Marco Daperno]]"
  - "[[Tim Raine]]"
  - "[[Isabelle Cleynen]]"
  - "[[Shaji Sebastian]]"
published: 2025-08-12
created: 2026-05-10
description: "Abstract. In this narrative review we present the current status of developments in artificial intelligence (AI) in the field of inflammatory bowel disease"
tags:
  - "clippings"
---
## Abstract

In this narrative review we present the current status of developments in artificial intelligence (AI) in the field of inflammatory bowel disease (IBD) surgery. We lay the foundations for how IBD surgery can implement the potential opportunities offered by AI technology. The main areas of potential utility are in the areas of surgical training, risk prediction in the pre-, intra-, and postoperative period in IBD patients undergoing surgery, and in IBD surgical research. We need to be mindful of the potential challenges in implementation and acceptability of these technological advances and put in mitigating measures to ensure transparency and equitable access. Global collaboration will be the cornerstone for such ventures.

## 1\. Introduction

Surgery in inflammatory bowel disease (IBD) remains a slow-growing field, marked by global disparities in access, choice and types of surgery, complications, and postoperative complications and mortality. A comprehensive approach to surgical system strengthening is required, including enhanced access, education, issue detection and treatment, and enhanced system efficiency.

In recent years, advances in artificial intelligence (AI) have augmented the delivery of healthcare services around the world, including foundation model architectures, wearable technologies, and biomedical research. Research shows that AI has the capacity to exceed or complement human skills with transformative potential across many fields, including finance, healthcare, and biomedical research. The technology’s biggest impact has been in the diagnostic specialties, such as radiology, pathology, and dermatology. More recently AI is expanding its footprint into surgical specialities, especially in ophthalmology, cardiothoracic surgery, and vascular surgery, demonstrating its potential as a transformative tool in the operating room. Although has not replaced surgeons, it offers opportunities to meet the global challenges in surgery.

As our knowledge and research of AI increases, surgical advancements are subsequently being achieved and integrated into our healthcare systems. The potential current and future role of AI in IBD surgery has been poorly investigated.

This review aims to map the existing use of AI in surgery with a focus on the field of IBD, exploring real-world applications, evaluating the effectiveness of AI models, and identifying gaps in current knowledge. By doing so, this review seeks to provide a foundation for further research and advancements in AI-driven surgical approaches in IBD and contribute to the broader understanding of AI’s potential impact on surgical sciences.

## 2\. Methods

The European Crohn’s and Colitis Organisation (ECCO) commissioned a scientific workshop consensus group on the subject of AI in IBD. Following an open call across all ECCO members, 15 participants were selected based on their expertise, and four subgroups were formed. This article highlights the topic of a working group focused on surgical aspects of AI in IBD. The idea of this review was discussed at the ECCO scientific workshop kick-off meeting in October 2023.

Because of different topics to be covered by this review, the authors made a pragmatic choice to conduct it as scoping review. The study aimed to combine a comprehensive literature search on the current use of AI in IBD surgery.

### 2.1. Literature search

Two independent authors (G.P. and A.S.) conducted a systematic literature search was conducted querying three electronic databases (MEDLINE, Embase, and Google Scholar). Eligible articles that investigated the role of AI in IBD surgery were assessed. The authors also searched the reference section of each eligible article to identify any additional relevant studies. Original studies, randomized controlled trials (RCTs), and reviews in all languages were included, irrespective of the publication’s date. Priority was given to IBD surgery, but papers containing AI concepts used in other fields of surgery which are applicable to the IBD surgical field were also considered. The last date of the search was August 1, 2024.

### 2.2. Search thread

The following terms were searched:

Search: ((artificial intelligence \[Title/Abstract\]) OR (machine learning \[Title/Abstract\])) OR (neural networks \[Title/Abstract\]) AND (((surgery \[Title/Abstract\]) OR (surgical \[Title/Abstract\])) OR (surgeon \[Title/Abstract\])) OR (operation \[Title/Abstract\]))

AND (((Inflammatory bowel disease \[Title/Abstract\]) OR (crohn’s disease \[Title/Abstract\])) OR (ulcerative colitis \[Title/Abstract\])) OR (IBD \[Title/Abstract\])

The choice of this broad search thread was a pragmatic choice aiming to include most of the studies about the topic.

### 2.3. Included studies

From 212 hits, 52 studies were assessed in full text and 25 studies were included in the final assessment.

We focused on already conducted reviews that had investigated AI in surgical treatment including the whole surgical journey from surgical planning, preoperative assessment to postoperative outcomes. We selected only areas in which AI application has been documented in scientific studies and excluded reviews speculating on the future role of AI. Studies regarding screening, diagnosis, and prognosis (without surgical intervention) were excluded. We included in this review papers until August 1, 2024.

### 2.4. AI in surgical education and training of IBD surgeons

Surgical training requires a combination of clinical knowledge and technical skill development. Traditionally, technical skill has been gauged through case volume, but this approach has proven inadequate as a reliable measure of surgical proﬁciency.<sup>1</sup> Validated tools such as the Objective Structured Assessment of Technical Skills (OSATS), the Global Operative Assessment of Laparoscopic Skills (GOALS), and the Global Evaluative Assessment of Robotic Skills (GEARS) offer structured methods for evaluating a trainee’s proﬁciency during minimally invasive surgery. However, these tools depend on direct observation by expert surgeons, which is constrained by factors such as limited working hours, ethical concerns regarding patient safety, and the potential for bias and interobserver variability. As a result, surgical educators are increasingly moving towards automated, objective, and data-driven assessments to support skill evaluation and provide feedback that enables independent, competency-based practice.<sup>2</sup>

Automated performance metrics (APMs), or objective performance indicators (OPIs), leverage data directly from surgical tools, such as robotic instruments, to evaluate technical proficiency. Metrics, such as instrument path length, bimanual dexterity, and idle time, have been shown to distinguish between novices, expert, and even super-expert levels of performance. These tools provide objective, detailed insights that can detect subtle fluctuations in skill levels, often missed by human evaluators. While promising, APMs currently face challenges, including the lack of universally accepted standards for assessment, leading to variability in their application. Research efforts are ongoing to refine APMs, with groups working on validation and improvement of these metrics, as well as developing accessible software to facilitate their adoption in surgical education and training.

Surgical phase recognition refers to the identification of different steps and phases of an operation.<sup>3</sup> By combining APMs with surgical phase recognition, computer vision systems can provide a comprehensive understanding of the surgical workflow. Ultimately, this integration will help to automate the analysis of surgical videos, enable objective assessments, facilitate surgical education and training, support quality improvement efforts, and enhance our understanding of the surgical process as a whole.<sup>3</sup> Advances in computer vision will also be reflected in improvement in surgical simulators equipped with virtual and augmented realities technologies.<sup>4</sup>

Although the measurement of APMs is still in early stages, it is a promising field with the potential to significantly support the training of junior surgeons as well as enhance performance of senior surgeons, reducing the reliance on real-world operations. This may alleviate the need for high volumes to attain technical expertise, which is a current challenge in colorectal surgery. With increased investment in this area, training of surgeons from low- and middle-income countries (LMICs) might be achieved without the need for prolonged residency programs in high-income countries. This advancement would be particularly beneficial for surgeons who plan to focus on IBD.

Studies on the implementation of AI in medical education show high accuracy in assessing students’ experiences and performance in diagnosing acute abdominal pain with the AI accurately classifying skilled and novice participants as well as evaluating surgical training levels.<sup>5</sup>

### 2.5. AI in surgical risk prediction and decision support in IBD

Risk prediction models are used routinely in healthcare practice, helping clinicians identify high-risk patients and make treatment decisions to allocate healthcare resources effectively.<sup>6</sup>

Surgery is a complex intervention <sup>7</sup> that can be affected by numerous factors before, during and after the operations, as shown in Figure 1. Building predictive models to aid in decision-making is thus a very complex task. AI, with its ability to analyze complex large datasets and uncover subtle patterns invisible to human observers, offers a promising solution.<sup>8</sup> While the field of AI in surgical outcome prediction is still in its infancy,<sup>9</sup> ongoing research and development could significantly enhance these capabilities. AI-driven models can predict short-term outcomes such as speed of recovery, length of postoperative hospital stay, complication rates, re-admission rates, and risk of re-intervention. Long-term outcomes such as functional outcomes, remission rates, and recurrence after IBD surgery can also be modelled. Such predictions will be instrumental for planning and cost reduction for the following reasons:

Figure 1.

Multitude of pre-, intra- and postoperative factors can affect surgical outcomes. AI can help in building a model for surgical intervention. 

[Open in new tab](https://academic.oup.com/view-large/figure/560487523/jjaf135f1.tif) [Download slide](https://academic.oup.com/DownloadFile/DownloadImage.aspx?image=https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/20/4/10.1093_ecco-jcc_jjaf135/1/jjaf135f1.jpeg?Expires=1780830082&Signature=V7OOeuEx06xwZs75bsnuLs22B7SRlMe-ICVdMRhCJItZTVmu93gI~cTpy8csQWD-E1VdCWTGdGIBfIr4VoWSWKLHcH4H5-OCjmXhkbRNCqXJdy7gj9oanllN~vk~RVMUcqt6iNunjd-UXbixNSCtwEltZ5fzVWBBxLlA87Y8uZYvJgGj7fF~IZmHwkHUpNE91ZOohtA3JPWB7NN7y21BDyleRAsWB3pxzGb--VPJ-Oq61oJdQtK2FRtBcgSmdIzWBH08P4zLhHHMjGNkgpKaA9-PZKaLcL1qtmcTionTpjLhVo7vyLkTrsATe9cBW7NMQF5eUVyh0G1BdwNDMmNiMw__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA&sec=560487523&ar=8232298&xsltPath=~/UI/app/XSLT&imagename=&siteId=5398)

1. As the population ages, the demand to consider performing surgical procedures is expected to rise. The decision to perform surgery and the choice of surgical intervention will increasingly depend on predictions regarding postoperative recovery and the predicted time to for a patient to return to habitual functions. There are currently no objective prediction models available to guide clinicians in this complex decision-making process. These decisions are usually based on clinical judgement, which can be affected by many subjective factors.<sup>10</sup> Effective prediction models will not only help in decision-making but also facilitate planning for postoperative care after discharge from the hospital, involving key stakeholders such as social services, physiotherapists, and patients’ families. Advances in digital health and medical technology will transform this area by improving access and affordability.<sup>11</sup>
2. Improving pre- and postoperative pathways: AI can facilitate the improvement of pre-, intra- and postoperative pathways. Well-designed studies leveraging AI to optimize prehabilitation, intraoperative monitoring, and postoperative recovery is essential. Objective measures of the effectiveness of these interventions can be used to refine the entire surgical journey in IBD patients.<sup>12</sup> Prediction models can also help quantify changes in recovery pathways, guiding adjustments to improve outcomes.
3. Defining the outcome measures: the most frequent used outcomes, such as the rate of postoperative complications, length of postoperative hospital stay, and readmission rates, fail to fully capture the nuances of surgical success. Metrics like disease-free survival, overall survival, and patient-reported outcome measures (PROMs) provide additional insights, but lack the objectivity needed to assess factors such as timing of the intervention, the effect of preoperative optimization, adequacy of the surgical technique, and the quality of postoperative care. AI can help bridge this gap by providing a data-driven, comprehensive framework for evaluating outcomes.<sup>9</sup> In IBD, some studies have attempted to use AI to predict the risk of surgery in patients with Crohn’s disease,<sup>13</sup> ulcerative colitis,<sup>14</sup> and acute severe ulcerative colitis.<sup>15</sup>
4. Optimization of the process: if we can improve each step in the pre-, intra-, and postoperative intervention by even 1% then the marginal gains theory tells us that we shall get a significant improvement in overall performance and thus outcomes. The ultimate goal of prediction models is to support surgical decision-making. Surgeons face high stakes and make complex decisions, influenced by time constraints, uncertainty, complexity, decision fatigue, and hypothetical-deductive reasoning. Properly applied, AI has the potential to augment this process by offering objective insights into whether to operate, identifying and mitigating modifiable risk factors, recognizing and managing complications and optimizing resource utilization, and actually conducting an operation.<sup>10</sup>

### 2.6. AI in surgical research

The improvement in prediction models and decision support systems based on AI algorithms will provide huge amounts of data that will transform surgical research. As we showed above, building an AI-based model for surgical interventions will enable researchers to fine-tune the model and improve processes and outcomes. This approach allows for better understanding and weighting of the effect of pre-, peri-, and postoperative interventions such as nutritional support (preoperative), extent of dissection (intraoperative) and intravenous fluid load (postoperative) as illustrated in Figure 1. These areas remain topics of active debate and research.

Traditional RCTs are less applicable to surgery since it is virtually impossible to deliver the identical intervention to different patients. Recording and adjusting for confounders will get us so far, but AI has the capacity to measure much more and report/adjust for patterns in the data for which conventional statistical approaches might not be suitable. AI-driven surgical models will also help to better understand the effects of under-studied factors such as team structure, time of operation, and air flow in the operating room. By incorporating these factors, researchers can develop more precise and objective outcome measures such as model efficiency to complement traditional outcomes such as postoperative complications (assessed by physicians) and PROMs (assessed by the patients themselves).<sup>9</sup> A particularly exciting development is the creation of digital twins that can be used for simulated surgical interventions including computer simulation models of surgical interventions that can be studied prior to conducting trials on patients. In the future there is a need to develop algorithms to measure the effect of surgical interventions in clinical trials.

AI models provide the foundation for big data mining (Figure 2). Previous studies using such approaches have focused on genetic and medical treatment aspects but are gaining traction in IBD surgery. Implementation in surgery was investigated by Nguyen et al.<sup>16</sup> who examined surgical outcomes including longitudinal disease activity and complications. Another use of big data mining in surgery has been to detect lymph node metastasis,<sup>17-20</sup> in the management of colorectal polyps,<sup>21</sup> and to improve surgical workflow and efficiency.<sup>22</sup>

Figure 2.

Data generated from AI models will be used for big data mining. However, efficient data mining requires objective big data. Big data is defined by the five “Vs”: volume, velocity, value, variety, and veracity.

[Open in new tab](https://academic.oup.com/view-large/figure/560487529/jjaf135f2.tif) [Download slide](https://academic.oup.com/DownloadFile/DownloadImage.aspx?image=https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/ecco-jcc/20/4/10.1093_ecco-jcc_jjaf135/1/jjaf135f2.jpeg?Expires=1780830082&Signature=wGkfDqmLvcZIwlXd1SQcuGo8sLa4gUWpaR-wvLti1TJHHY97yOIdVLIGRNClrrF1Ez4S~PYu9fQnMHU8VmuFN6vOiTaR0I3mV8jmQsRKb4j52OA~zWEwVdCl36qB83myNgjjdUqpuCS8RJJBsNOZiuvWm5n0cf4zi9Q-P4XgGaAPtOALipv5PD6D6Hx37-tJnKYliiJDtkm7qzD3vzpHK9s2ucELOkJNcciFsbQJlxizkl2CCfsVyqXRC6slSHobrOTdoolo2T1T9ottUlm33iXHZTxQ-adXovppUJ0pEoYCV6-0l6AvmNm31R7vqtABpgUT4DlNh4bK5bPW1krMmg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA&sec=560487529&ar=8232298&xsltPath=~/UI/app/XSLT&imagename=&siteId=5398)

Moreover, AI-generated models have been explored as a tool for prognosis.<sup>23-26</sup>

Despite these advances, the integration of medical data to train AI presents significant challenges as the data are spread across different platforms, for example radiological systems and electronic medical records (EMRs). This fragmentation can limit AI’s ability to integrate information effectively, which is crucial for making accurate predictions and supporting clini­cal decisions. Addressing this will require building ready-to-use AI-integrated ecosystems that prioritize data accuracy, data privacy, and security.

With the rapid computerization of health research, the volume of electronic data continues to grow exponentially, encompassing large audit databases, published academic literature, EMRs, and online data storage. This increasing data availability underscores the need to explore innovative methods for efficiently accessing, integrating, and harnessing these data to advance research.

Natural language processing (NLP), a branch of AI focused on enabling computers to understand and interpret human language, may offer a solution to these challenges, including through its role in the automated labeling and categorization of significant quantities of unstructured data.<sup>22</sup><sup>,</sup><sup>27</sup> This technology analyzes large amounts of unstructured text, such as narrative text found in EMRs. In surgical care, NLP has been used to automatically review EMRs, searching for specific words and phrases in operative reports and progress notes that help predict complications such as anastomotic leaks after colorectal surgery.<sup>28</sup> There are algorithms that predict outcomes based on straightforward clinical factors that surgeons typically consider, such as the type and complexity of the surgery <sup>12</sup> However, such algorithms also provide nuanced descriptive terms about patients (eg, “irritated” or “tired”) in relation to the day after surgery, allowing them to predict outcomes such as leaks with high accuracy.<sup>12</sup> In a review by Yang et al.<sup>27</sup> the authors examined 148 studies of the use of NLP with EMRs and concluded that improving the performance of AI can help patients receive more evidence-based and accurate treatments.

Other uses of NLP are preoperative triaging, the referral process, generating operative notes, and patient follow-up.<sup>22</sup> To produce models that may be integrated with any EMRs in any setting, data must be standardized. NLP might improve efficiency and afford surgeons more time in the operating room for greater job satisfaction.<sup>29</sup>

A recent review raised concerns about the reproducibility of AI research, and pointed to the lack of transparency in data, code, and model as fundamental reasons.<sup>30</sup> Addressing these challenges is crucial for ensuring the reliability of AI-backed systems in surgical research. Future advancements may include AI-enhanced systems to identify flaws in study design and support more robust scientific publishing processes.

### 2.7. Limitations and perils of AI

A recent review raised concerns about the reproducibility of AI research and pointed to a lack of transparency in data, code, and model as fundamental reasons.<sup>30</sup> The expected AI backed systems to scrutinize flows in design of studies and AI enhanced scientific publishing of research are areas to be explored in the future. The accuracy and reliability of AI outputs depend on the quality and type of data it uses. Biases in how clinical data are collected can influence the patterns AI identifies and the predictions it generates.<sup>12</sup> A significant challenge with AI algorithms is the difficulty in interpreting their processes (the so-called “black box”). While these systems can identify patterns that humans might overlook, researchers often struggle to determine how or why the computer arrived at specific conclusions. Indeed, studies have shown that different models can predict risks for the same patients very differently despite exhibiting similar model performances.<sup>6</sup>

Therefore, interpretability, safety, and rigorous monitoring must be secured before any decision support system can get ethical approval. Initial implementation of such systems should occur on a small scale, akin to phase 1 and 2 clinical trials for experimental medications, with close monitoring to analyze their effects across populations and individual patients.<sup>10</sup> AI is not a solution for all problems. Simply using AI models does not guarantee improved performance over traditional methods. Moreover, model validation procedures are often not sound or not well reported, which hampers a fair model comparison in real-world case studies.<sup>31</sup>

Another limitation that can lead to poor AI-based studies is a lack of sample size calculation leading to studies being underpowered to precisely estimate overall risk.<sup>32</sup>

The lack of external validation is another methodological flaw in many, if not most, AI-based studies. Before considering whether to use a multivariable (diagnostic or prognostic) prediction model, it is essential that its performance is evaluated using data not included in its development—a process referred to as external validation.<sup>33</sup> Plana et al.<sup>33</sup> examined RCTs using AI and found that despite the large number of medical machine learning algorithms in development, few RCTs for these technologies have been conducted. Among the published RCTs, there was high variability in adherence to reporting standards, risk of bias, and a lack of participants from underrepresented minority groups.<sup>34</sup> The poor methodology was also highlighted by a systematic review by Navarro et al. who found that most studies on AI-based prediction have a high risk of bias. Factors contributing to this risk of bias include small study sizes, poor handling of missing data, and failure to deal with overfitting. Efforts to improve the design, conduct, reporting, and validation of such studies are necessary to boost the application of machine learning-based prediction models in clinical practice.<sup>35</sup> Finally, there are issues about data privacy and ethical considerations associated with the implementation of AI, as detailed in two recent reviews.<sup>36</sup><sup>,</sup><sup>37</sup>

These limitations may explain why most clinical decision support systems achieve only small to moderate improvements in targeted processes of care,<sup>38</sup> a finding confirmed by the small changes in clinical endpoints in such studies.<sup>39</sup>

## 3\. Discussion

This review explored the integration of AI into surgical care, specifically focusing on its applications in IBD. The findings underscore the transformative potential of AI while acknowledging that its current implementations do not always surpass traditional methods.

Our review aligns with prior studies indicating that APMs reliably differentiate levels of surgical expertise, revealing subtle variations undetectable by human evaluators.<sup>7</sup> The integration of APMs into surgical education could revolutionize technical training, especially in resource-limited settings. For instance, there is the potential to train IBD surgeons in LMICs with reduced reliance on residency programs. Additionally, surgical phase recognition has shown promise in automating workflow analysis and training feedback systems. These findings echo those of Hashimoto et al., who emphasized the transformative impact of phase recognition in improving intraoperative efficiency and surgical education. However, the variability in assessment standards and lack of validation across settings remain barriers to widespread adoption, as noted in other reviews.<sup>40</sup>

In terms of surgical risk prediction, our review highlights the capacity of AI to analyze large datasets and model complex interactions, enabling predictions of outcomes such as postoperative recovery, complications, and remission rates in IBD surgery. However, AI’s integration into decision support systems also remains a work in progress. While some studies report improved surgical decision-making and resource allocation, others note only incremental improvements in care processes and clinical endpoints.<sup>37</sup> This observation aligns with the findings of systematic reviews by Navarro et al. and Plana et al., which identified methodological flaws, including small sample sizes, overfitting, and limited external validation in AI-based clinical studies.<sup>35</sup><sup>,</sup><sup>36</sup> Addressing these limitations is essential to realizing the full potential of AI in surgical decision support.

### 3.1. Strengths and opportunities

We advocate better modelling of surgical interventions to allow AI-based identification of previously underexplored factors influencing outcomes, such as team dynamics, operative timing, and air flow in the operating room.<sup>7</sup><sup>,</sup><sup>9</sup> These capabilities align with findings from Nguyen et al., who demonstrated the power of AI in identifying predictors of surgical outcomes through big data analysis.<sup>18</sup>

Resource-poor health institutions face limitations in local equipment, personnel expertise, infrastructure, data-rights frameworks, and public policies and can benefit from the adoption of AI.<sup>41</sup>

Future research must focus on creating standardized and objective metrics for AI-based studies in surgery. Digital twin technology, for example, represents an exciting frontier for simulating surgical interventions before clinical trials, allowing researchers to fine-tune approaches and improve outcome predictability.<sup>11</sup> Expanding these models to IBD surgery could significantly enhance research precision and reduce procedural costs.

### 3.2. Challenges and limitations

Despite its promise, integrating AI into IBD surgery faces critical limitations. Methodological flaws in current studies, such as inadequate sample size calculations and poor reporting of validation methods, have hampered its clinical translation.<sup>32</sup><sup>,</sup><sup>33</sup> Moreover, the “black box” nature of many AI algorithms often obscures their decision-making processes, raising concerns about interpretability and trustworthiness.<sup>14</sup>

The ethical and infrastructural barriers to implementing AI in LMICs also persist. While our findings highlight the potential of AI to reduce surgical inequalities, achieving this requires substantial investment in education, infrastructure, and phased deployment. Studies have consistently emphasized the need for adaptable AI frameworks that account for resource disparities.<sup>40</sup>

## 4\. Conclusion

This review affirms the transformative potential of AI in IBD surgical care, spanning applications in training. decision support, and research. However, realizing this potential requires addressing the methodological, ethical, and infrastructural challenges identified. Further research should focus on rigorous external validation, transparent reporting, and equitable access to AI technologies. By overcoming these barriers, AI could significantly improve surgical outcomes and advance global surgical equity.

## Author contributions

This paper was a joint expert consensus activity. All authors participated intellectually and practically in this work and take public responsibility for the content of the article, including conception, design, data interpretation, and writing/review of the manuscript. All authors and the ECCO Governing Board approved the final version for submission.

## Funding

None declared.

## Conflicts of interest

None declared.

## References

Gillani

M

,

Rupji

M

,

Paul Olson

TJ

, et al..

Surgery (United States)

.

2024

;

176

:

1036

\-

1043

.

Hung

AJ

,

Chen

J

,

Ghodoussipour

S

, et al..

BJU Int

.

2019

;

124

:

487

\-

495

.

Garrow

CR

,

Kowalewski

KF

,

Li

L

, et al..

Ann Surg

.

2021

;

273

:

684

\-

693

.

Alaker

M

,

Wynn

GR

,

Arulampalam

T.

.

Int J Surg

.

2016

;

29

:

85

\-

94

.

Tozsin

A

,

Ucmak

H

,

Soyturk

S

, et al..

Surg Innov

.

2024

;

31

:

415

\-

423

.

Li

Y

,

Sperrin

M

,

Ashcroft

DM

,

Van Staa

TP.

.

BMJ

2020

;

371

:

m3919

El-Hussuna

A

,

Lange

J.

.

Dan Med J

.

2022

;

69

:

A205119

.

Bektaş

M

,

Tuynman

JB

,

Costa Pereira

J

, et al..

World J Surg

.

2022

;

46

:

3100

\-

3110

.

El-Hussuna

A.

\[Internet\].

2024

. Oct 24 \[cited 2024 Nov 18\];

19

:

1

\-

2

. Available from: [https://www.ecco-ibd.eu/publications/ecco-news/item/2024-3-outcomes-in-ibd-surgery-are-they-adequate.html](https://www.ecco-ibd.eu/publications/ecco-news/item/2024-3-outcomes-in-ibd-surgery-are-they-adequate.html)

Loftus

TJ

,

Tighe

PJ

,

Filiberto

AC

, et al..

JAMA Surg

.

2020

;

155

:

148

\-

158

.

Tang

HHY

,

Mok

E

,

Yeung

HS

, et al.

Eur J Surg Oncol

.

2024

;

50

:

108376

.

Hashimoto

DA

,

Rosman

G

,

Rus

D

,

Meireles

OR.

.

Ann Surg.

2018

;

268

:

70

\-

76

.

Dong

Y

,

Xu

L

,

Fan

Y

, et al..

Medicine (Baltimore)

.

2019

;

98

:

e17510

.

Takayama

T

,

Okamoto

S

,

Hisamatsu

T

, et al..

PLoS One

.

2015

;

10

:

e0131197

.

Jain

S

,

Kedia

S

,

Sethi

T

, et al..

J Gastroenterol Hepatol

.

2018

;

33

:

615

\-

622

.

Nguyen

NH

,

Picetti

D

,

Dulai

PS

, et al..

J Crohns Colitis

.

2022

;

16

:

398

\-

413

.

Cheong

C

,

Kim

NW

,

Lee

HS

,

Kang

J.

.

Langenbecks Arch Surg

.

2024

;

409

:

287

.

Yao

X

,

Zhou

Z

,

Mao

S

, et al..

J Surg Oncol

.

2024

;

130

:

637

\-

643

.

Abbaspour

E

,

Karimzadhagh

S

,

Monsef

A

, et al..

Int J Surg

.

2024

;

110

:

3795

\-

3813

.

Thompson

N

,

Morley-Bunker

A

,

McLauchlan

J

, et al..

BJS Open

.

2024

;

8

:

zrae033

.

Hassan

C

,

Rizkala

T

,

Mori

Y

, et al.;

CADx analysis study group

..

Lancet Gastroenterol Hepatol

.

2024

;

9

:

1010

\-

1019

.

Le

KDR

,

Tay

SBP

,

Choy

KT

, et al..

Front Surg

.

2024

;

11

:

1403540

.

Kokkinakis

S

,

Ziogas

IA

,

Llaque Salazar

JD

, et al..

Cancers (Basel)

.

2024

;

16

:

1645

.

Bedrikovetski

S

,

Seow

W

,

Kroon

HM

, et al..

Eur J Radiol

.

2022

;

149

:

110218

.

Vergara-Fernandez

O

,

Trejo-Avila

M

,

Salgado-Nesme

N.

.

World J Clin Cases

.

2020

;

8

:

1188

\-

1202

.

Cho

HJ

,

Kang

J.

.

Ann Surg Treat Res

.

2024

;

106

:

305

\-

312

.

Yang

X

,

Mu

D

,

Peng

H

, et al..

JMIR Med Inform

.

2022

;

10

:

e33799

.

Mellia

JA

,

Basta

MN

,

Toyoda

Y

, et al..

Ann Surg

.

2021

;

273

:

900

\-

908

.

Rengers

TA

,

Thiels

CA

,

Salehinejad

H.

.

JAMA Surg

.

2024

;

159

:

445

\-

450

.

Kocak

B

,

Yardimci

AH

,

Yuzkan

S

, et al..

Acad Radiol

.

2023

;

30

:

2254

\-

2266

.

Christodoulou

E

,

Ma

J

,

Collins

GS

, et al..

J Clin Epidemiol

.

2019

;

110

:

12

\-

22

.

Dhiman

P

,

Ma

J

,

Qi

C

, et al..

BMC Med Res Methodol

.

2023

;

23

:

188

.

Collins

GS

,

De Groot

JA

,

Dutton

S

, et al..

BMC Med Res Methodol

.

2014

;

14

:

40

.

Plana

D

,

Shung

DL

,

Grimshaw

AA

, et al..

JAMA Netw Open

.

2022

;

5

:

e2233946

.

Andaur Navarro

CL

,

Damen

JAA

,

Takada

T

, et al..

BMJ

2021

;

375

:

n2281

.

Morris

MX

,

Song

EY

,

Rajesh

A

, et al..

Am Surg

.

2023

;

89

:

55

\-

60

.

Safdar

NM

,

Banja

JD

,

Meltzer

CC.

.

Eur J Radiol

.

2020

;

122

:

108768

.

Moja

L

,

Polo Friz

H

,

Capobussi

M

, et al..

JAMA Netw Open

.

2019

;

2

:

e1917094

.,

Kwan

Janice L

,

Lo

Lisha

,

Ferguson

Jacob

, et al..

BMJ.

2020

:

370

:

m3216

.

Chen

A

,

Ghodoussipour

S

,

Titus

MB

, et al..

World J Urol

.

2020

;

38

:

1615

\-

1621

.

Mollura

DJ

,

Culp

MP

,

Pollack

E

, et al..

Radiol

.

2020

;

297

:

513

\-

520

.