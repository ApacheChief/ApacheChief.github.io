---
layout: post
author: Dennis Tan (8903784Y)
title: "Applied Data Science Project Documentation"
categories: ITD214
---
## Project Background
This is my project for ITD214 Applied Data Science Project. This module is in partial fulfillment of Post Diploma Certificate (PDC) 2 Applied Data Science

The purpose of this content is to showcase the work completed for the above module. This is a team project in which members are required to source and scrape data from the web and apply Machine Learning (ML) techniques to generate insights, outputs, and recommendations in accordance with the CRISP-DM framework (Wirth & Hipp, 2000). For the purpose of this project, only stages 1 to 5 of the CRISP-DM framework are required.
The title of the project is: **“Enhancing Sportswear Apps User Experience through Review Analytics.”** Anonymised data was obtained from Kaggle’s dataset **“Sportswear App Reviews (Google Play)”** by Kris Bruurs (Oct/Nov 2025). The data was curated through Google Play, which complies with Google Play’s terms and aligns with GDPR (EU) and PDPA (Singapore) standards (Google Cloud, n.d.; PDPC, n.d.).
## Work Accomplished
Document your work done to accomplish the outcome

### Data Preparation
![CRISP-DM Framework](https://github.com/user-attachments/assets/2de5b520-94f2-4190-a5b7-41c95f225592)



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
