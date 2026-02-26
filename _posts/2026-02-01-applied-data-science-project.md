---
layout: post
author: Dennis Tan (8903784Y)
title: "Applied Data Science Project Documentation"
categories: ITD214
---
## I Project Background
This is my project for ITD214 Applied Data Science Project. This module is in partial fulfillment of Post Diploma Certificate (PDC) 2 Applied Data Science

The purpose of this content is to showcase the work completed for the above module. This is a team project in which members are required to source and scrape data from the web and apply Machine Learning (ML) techniques to generate insights, outputs, and recommendations in accordance with the CRISP-DM framework (Wirth & Hipp, 2000). For the purpose of this project, only stages 1 to 5 of the CRISP-DM framework are required.
The title of the project is: **“Enhancing Sportswear Apps User Experience through Review Analytics.”** Anonymised data was obtained from Kaggle’s dataset **“Sportswear App Reviews (Google Play)”** by Kris Bruurs (Oct/Nov 2025). The data was curated through Google Play, which complies with Google Play’s terms and aligns with GDPR (EU) and PDPA (Singapore) standards (Google Cloud, n.d.; PDPC, n.d.).
##  II. Work Accomplished
###  II.I Business & Data Understanding
## Business Understanding
• 	Goal: uncover recurring themes in user reviews to improve sportswear app UX.
• 	Why topic modelling matters: identifies operational pain points and UX strengths.
## Data Understanding
• 	Dataset: 6,446 Google Play reviews (Nike, Adidas, Puma, Gymshark).
• 	Key fields used: brand, score, content.
• 	Observations: skew toward positive ratings, Gymshark fewer reviews, varied text length.
## II.II Data Preparation 
• 	Cleaning and preprocessing: lowercasing, punctuation removal, stopwords, lemmatisation, negation handling.
• 	Feature engineering: review length, time features, sentiment labels.
• 	Handling missing data (e.g., sparse , skewed ).
• 	Dataset recap: 6,446 reviews → cleaned dataset of 6,328 rows × 12 columns.
## II.III Modelling 
• 	Topic Modelling (Objective 1):
• 	LDA (coherence score tuning, interpretable clusters).
• 	BERTopic (contextual but fragmented clusters).
• 	Comparative analysis (cross‑validation of insights).

## II.IV. Evaluation & Recommendations
• 	Model performance metrics (coherence vs perplexity).
• 	Analytical Limitations and Gaps:
• 	Reliance on rating scores as proxy for satisfaction.
• 	Sparse developer response data.
• 	Brand imbalance.
• 	External factors not incorporated.
.   Appropriate recommendations grounded on operations management and marketing principles
## II.V AI Ethics: 
 Addressed: Privacy, Fairness, Accuracy, Accountability, Transparency issues.
 
## Chapter 1: Introduction & Framework
## 1.1	Project Context
The requirement of this project is to make use of ML techniques that we have learnt in both PDC1 & 2 to deliver solutions with insights for business. The objective of our project is to  enhance sportswear app experience through the application of learnt analytics so as to  provided insights, evaluation and deliver appropriat recommendations for improvements to the app in order to enhance user experience.

The purpose of this content is to showcase the work completed for the above module. This is a team project in which members are required to source and scrape data from the web and apply Machine Learning (ML) techniques to generate insights, outputs, and recommendations in accordance with the CRISP-DM framework (Wirth & Hipp, 2000). For the purpose of this project, only stages 1 to 5 of the CRISP-DM framework are required.
The title of the project is: **“Enhancing Sportswear Apps User Experience through Review Analytics.”** Anonymised data was obtained from Kaggle’s dataset **“Sportswear App Reviews (Google Play)”** by Kris Bruurs (Oct/Nov 2025). The data was curated through Google Play, which complies with Google Play’s terms and aligns with GDPR (EU) and PDPA (Singapore) standards (Google Cloud, n.d.; PDPC, n.d.).

## 1.2	Objectives: 
To achieve this, our team decided to apply text analytics of topic modelling, sentiment analysis and predictive modelling, which will all contribute to the overall insights and with these insights recommend enhancements to the app.
The first objective that I’m responsible for applies topic modelling to suss out what users talk about to derive recurring themes across the 4 brands (Nike, adidas, Puma & Gymshark).

 
## 1.3	Methodological Framework: CRISP DM stages (cite Wirth & Hipp, 2000).
In accordance with the project requirements,  our team followed the Cross Industry Standard Process for Data Mining  (CRISP-DM). The first part of our presentation covers stages 1 to 3 (Business Understanding to Data Preparation) while the 2nd and final presentation covers 4 & 5 (Modelling and Evaluation).  Stage 6 - Deployment  is out-of-scope for the purpose of this project.
 ![CRISP-DM Framework](https://github.com/user-attachments/assets/2de5b520-94f2-4190-a5b7-41c95f225592)
                 <p align = "center"> Source: Wirth & Hipp, 2000 </p>

## 1.4	Contribution: 
The use of topic modelling to perform discovery of app users is effectively tapping on the consumer pulse of the app users on their opinions of the app.  Topic modelling with the appropriate techniques applied will uncover both the breadth and depth of users’ sentiments and gain insights in areas where the app can be enhanced/improved.

## 2.1 Business Understanding
Mobile apps are keys to customer touchpoints for sportswear brands in the 21st century. Poor app experience will lead to low ratings, negative reviews and reduced app engagement, thereby reducing user retention and brand loyalty.
Users' reviews often contain rich but unstructured text and manual analysis is too time-consuming and if these reviews are not properly used insights from customers are often underutilised or ignored. 
Hence, there is need for a systematic, data-driven approach to understand users' concerns and satisfaction drivers.
The business goal is to **enhance user experience and engagement for the mobile applications** of the 4 brands  by leveraging on data-dirven insights derived from the reviews.
Our objectives are as follows:
i)	To identify key themes and recurring discussion topics across brands through topic modelling
ii)	To evaluation user sentiment and emotional tone using sentiment analysis techniques
iii)	To  determine the primary drivers of user satisfaction through statistical analysis and predictive modelling
To gain greater insights into the 4 brands, our team did research on the brand scale as expected review volume will likely be relative to the market size of each brand.
Below is summary table of brand scale and its expected review volume.
 
From the above table, Nike tops the chart in terms of size followed by adidas while Gymshark is the smallest of the 4 players.  Subequent exploratory will reveal that Gymshark’s review is substantially smaller than the rest of the brands.

### Data Preparation
## 2.2.1 Ethical Considerations
Our  anonymised dataset was obtained from Kaggle (Bruurs, 2005) and extracted using open-source google-play-scraper Python library. Reviews are pre-moderated by Google for quality and trustworthiness and since data use and collection complies with Google Play’s terms, it therefore aligns with GDPR(EU) and PDPA(Singapore) standards.
## 2.2.2 Size and Attribute of Dataset
The data set consisted of 6,446 Google Play reviews, and the following key fields:
i)	Brand
ii)	Score
iii)	at (date and time of review)
iv)	content (review text)
Fields like “review Id”, “reply_content”, “thumbs_up” and  “review_created_version” were either irrelevant or too sparse and were excluded from modelling.
For topic modelling the following fields were used:
i)	brand
ii)	score
iii)	content
## 2.2.3 Exploratory Data Analysis (EDA)
Initial EDA provided the schema of the dataset (ref: 2 – herein ref here refers to the Python script section number) Fig 
![Schema](/assets/images/Fig2_1%20-%20Schema.png)
![Data Audit](/assets/images/Fig2_2%20-%20Data%20Audit.png)
![Reply Content](/assets/images/Fig2_3%20-%20reply_content.png)
 
Initial data audit revealed sparsity of ‘reply_content’ ~ 93% (Fig 2.3) and attribute was hence not used.
Audit of Missing Values and Spares columns (Fig 2.4) reveals that there was no missing values in other columns besides “reply_content”.
Fig 2.4	Fig 2.5
 	 





### Modelling
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.
<img width="915" height="581" alt="image" src="https://github.com/user-attachments/assets/902f36ca-7e15-450c-aefe-d6efbac7624c" />

### Evaluation
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## Recommendation and Analysis
Explain the analysis and recommendations

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## AI Ethics

## Privacy
Given that app reviews can sometimes contain personal identifiers, the data was scraped from Google Play, where reviews are pre‑moderated by Google. This ensures compliance with Google Play’s terms and alignment with GDPR (EU) and PDPA (Singapore) standards. In addition, our team reviewed the dataset to confirm that no sensitive personal information was retained, thereby safeguarding user privacy during analysis.

## Fairness
**Risk:** Bias in the dataset (e.g., reviews skewed toward certain brands, demographics, or regions) can lead to unfair insights.  

**Mitigation:** Balanced sampling is applied, limitations are documented, and results are not overgeneralised. Any bias or imbalances are acknowledged through **Analytical Limitations and Gaps** (see slide 47 PPT).

## Accuracy
**Risk:** Machine Learning models may misclassify sentiment or context, leading to misleading recommendations.
**Mitigation:** Validate models with cross‑checks (e.g., LDA vs. BERTopic), and clearly state confidence levels and error margins.

## Accountability
**Risk:** If insights are misused (e.g., companies act on flawed recommendations), responsibility can be unclear.
**Mitigation:** We maintain transparent documentation of methods, assumptions, and limitations. Team members take responsibility for their own ouput, all modelling choices were documented in scripts and slides for lecturers' review.

## Transparency
**Risk:** Some machine learning models can be complex and difficult to interpret, which may obscure how decisions are made.  
**Mitigation:** We used interpretable models where possible (e.g., Naive Bayes, Decision Trees, Random Forest feature importance) and complemented them with explainable outputs such as topic modelling visualisations and labelled clusters. The rationale for model choices was documented to ensure clarity and lecturers' review.


## Source Codes and Datasets
Upload your model files and dataset into a GitHub repo and add the link here. 
