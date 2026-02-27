---
layout: post
author: Dennis Tan (8903784Y)
title: "Applied Data Science Project Documentation"
categories: ITD214
---
## I. Project Background
This is my project for ITD214 Applied Data Science Project. This module is in partial fulfillment of Post Diploma Certificate (PDC) 2 Applied Data Science

The purpose of this content is to showcase the work completed for the above module. This is a team project in which members are required to source and scrape data from the web and apply Machine Learning (ML) techniques to generate insights, outputs, and recommendations in accordance with the CRISP-DM framework (Wirth & Hipp, 2000). For the purpose of this project, only stages 1 to 5 of the CRISP-DM framework are required.

The title of the project is: **“Enhancing Sportswear Apps User Experience through Review Analytics.”** Anonymised data was obtained from Kaggle’s dataset **“Sportswear App Reviews (Google Play)”** by Kris Bruurs (Oct/Nov 2025). The data was curated through Google Play, which complies with Google Play’s terms and aligns with GDPR (EU) and PDPA (Singapore) standards (Google Cloud, n.d.; PDPC, n.d.).
##  II. Work Accomplished
###  II.I Business & Data Understanding
## Business Understanding
• 	Goal: uncover recurring themes in user reviews to improve sportswear app UX.

• 	Why topic modelling matters: identifies operational pain points and UX strengths.

## Data Understanding
• 	Dataset: 6,446 Google Play reviews (Nike, Adidas, Puma, Gymshark)

• 	Key fields used: brand, score, content

• 	Observations: skew toward positive ratings, Gymshark fewer reviews, varied text length

## II.II Data Preparation 

• 	Cleaning and preprocessing: lowercasing, punctuation removal, stopwords, lemmatisation, negation handling

• 	Feature engineering: review length, time features, sentiment labels

• 	Handling missing data (e.g., sparse , skewed )

• 	Dataset recap: 6,446 reviews → cleaned dataset of 6,328 rows × 12 columns
## II.III Modelling 

• 	Topic Modelling (Objective 1):

• 	LDA (coherence score tuning, interpretable clusters)

• 	BERTopic (contextual but fragmented clusters)

• 	Comparative analysis (cross‑validation of insights)


## II.IV Evaluation & Recommendations
• 	Model performance metrics (coherence vs perplexity)

• 	Analytical Limitations and Gaps:

  - 	Reliance on rating scores as proxy for satisfaction
  
  - 	Sparse developer response data
  
  - 	Brand imbalance
  
  - 	External factors not incorporated
  
Appropriate recommendations grounded on operations management and marketing principles

## II.V AI Ethics
 Addressed: Privacy, Fairness, Accuracy, Accountability, Transparency issues.
 
## Chapter 1: Introduction & Framework
## 1.1	Project Context
The project requires the use of ML techniques that we have learnt in both PDC1 & 2 to deliver business insights. The objective of our project is to  enhance sportswear app experience through the application of learnt analytics so as to  provide insights, evaluation and deliver appropriate recommendations for improvements to the app in order to enhance user experience.

The purpose of this content is to showcase the work completed for the above module. This is a team project in which members are required to source and scrape data from the web and apply Machine Learning (ML) techniques to generate insights, outputs, and recommendations in accordance with the CRISP-DM framework (Wirth & Hipp, 2000). For the purpose of this project, only stages 1 to 5 of the CRISP-DM framework are required.

The title of the project is: **“Enhancing Sportswear Apps User Experience through Review Analytics.”** Anonymised data was obtained from Kaggle’s dataset **“Sportswear App Reviews (Google Play)”** by Kris Bruurs (Oct/Nov 2025). The data was curated through Google Play, which complies with Google Play’s terms and aligns with GDPR (EU) and PDPA (Singapore) standards (Google Cloud, n.d.; PDPC, n.d.).

## 1.2	Objectives
To achieve this, our team decided to apply topic modelling, sentiment analysis and predictive modelling to generate insights and recommend enhancements to the app.

The first objective that I’m responsible for applies topic modelling to identify recurring themes in users discussions across the four brands: Nike, adidas, Puma & Gymshark.

 
## 1.3	Methodological Framework
In accordance with the project requirements,  our team followed the Cross Industry Standard Process for Data Mining  (CRISP-DM). The first part of our presentation covers stages 1 to 3 (Business Understanding to Data Preparation) while the 2nd and final presentation covers 4 & 5 (Modelling and Evaluation).  Stage 6 - Deployment  is out-of-scope for the purpose of this project.
 ![CRISP-DM Framework](https://github.com/user-attachments/assets/2de5b520-94f2-4190-a5b7-41c95f225592)
                 <p align = "center"> Source: Wirth & Hipp, 2000 </p>

## 1.4	Contribution
Topic modelling enables the discovery of user perspectives, effectively tapping into the consumer pulse of app reviews. With appropriate techniques, it uncovers both the breadth and depth of user sentiment and highlights areas for app enhancement.


## 2.1 Business Understanding
 
Mobile apps are critical customer touchpoints for sportswear brands in the 21st century. A poor app experience leads to low ratings, negative reviews, reduced engagement, and ultimately diminished user retention and brand loyalty.  

User reviews often contain rich but unstructured text. Manual analysis is time‑consuming, and without systematic processing, valuable customer insights risk being underutilised or ignored.  

Hence, a data‑driven approach is needed to understand users’ concerns and satisfaction drivers. The business goal is to **enhance user experience and engagement for the mobile applications of the four brands** by leveraging insights derived from reviews.  

Our objectives are as follows:  
i) To identify key themes and recurring discussion topics across brands through topic modelling  
ii) To evaluate user sentiment and emotional tone using sentiment analysis techniques  
iii) To determine the primary drivers of user satisfaction through statistical analysis and predictive modelling  

To gain deeper insights into the four brands, our team researched their relative market scale, as expected review volume is likely proportional to brand size.  

From this analysis, Nike tops the chart, followed by adidas, while Gymshark is the smallest player. Subsequent exploration confirms that Gymshark’s review volume is substantially lower than that of the other brands.


### 2.2 Data Preparation
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
Initial EDA provided the schema of the dataset (2 in the caption refers to the section in the Python script) Fig 2.1 & 2.2

<div style="text-align:center; margin-bottom: 1rem;"><div><strong>Fig 2.1 — Schema Snapshot</strong></div><img src="/assets/images/Fig2_1 - Schema.png" width="650"></div>
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 2.2 — Data Audit</strong></div>
  <img src="/assets/images/Fig2_2 - Data Audit.png" width="650">
</div>


 
An initial data audit revealed sparsity of ‘reply_content’ ~ 93% (Figs 2.3/2.5) and the attribute was hence not used.
Audit of Missing Values and Spares columns (Fig 2.4) reveals that there were no missing values in other columns besides “reply_content”
(Fig 2.4	Fig 2.5)
 	 
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 2.3 — reply_content Audit Output</strong></div>
  <img src="/assets/images/Fig2_3 - reply_content.png" width="650">
</div>

<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 2.4 — Audit of Missing Values (1 of 2)</strong></div>
  <img src="/assets/images/Fig2_4 -Audit of Missing 1 of 2.png" width="650">
</div>

<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 2.5 —Audit of Missing Values (2 of 2)</strong></div>
  <img src="/assets/images/Fig2_5 - Audit of Missing Values 2 of 2.png" width="650">
</div>

## 2.3 Cleaning & Preprocessing: Lowercasing, stopwords, lemmatization
## 2.3.1 Duplicate and Missing Content Audit
An audit was conducted on the key attributes—brand, content, and scores—to check for possible duplicates and missing values. The audit confirmed that no duplicates or missing entries were present, and all scores were valid within the expected range of 1 to 5 (Fig. 2.6).

<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 2.6 — Audit of Duplicates and Missing Contents</strong></div>
  <img src="/assets/images/Fig2_6 - Audit of Dup and Missing Contents.png" width="650">
</div>



 
## 2.3.2 Data Cleaning & Transformation
This section assigns appropriate dtype to brand  also compute review length to get a feel of the text length therein (Fig 2.7).

 <div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 2.7 — Data Cleaning and Transformation</strong></div>
  <img src="/assets/images/Fig2_7 - Data Cleaning and Transformation.png" width="650">
</div>

## 2.4 Post Transformation EDA
Words curated from research articles (Maalej et al., 2016; Guzman & Maalej, 2014; Iacob & Harrison, 2013)  were used to plot unigrams for an initial overview of the topics  (Fig 2.8a , 2.8b).
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 2.8a — Unigram Extraction</strong></div>
  <img src="/assets/images/Fig2_8a - Unigram.png" width="650">
</div>

<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 2.8b — Unigram Output</strong></div>
  <img src="/assets/images/Fig2_8b - Unigram Output.png" width="650">
</div>

To enrich the semantic representation of tokens, bigrams were also plotted. However, further cleaning was required, including lowercasing, removal of stopwords, numbers, and punctuation. Lemmatisation was selected over stemming, as research has shown that lemmatisation preserves the semantic meaning of tokens, whereas stemming often produces truncated or non‑dictionary forms that may distort topic representations (Jurafsky & Martin, 2021; Manning, Raghavan, & Schütze, 2008) – Fig. 2.9. 

<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 2.9 — Text Pre‑processing Workflow</strong></div>
  <img src="/assets/images/Fig2_9 - Text Pre-processing.png" width="650">
</div>

Thereafter, bi-grams extraction and brand-wise comparisons were plotted (Fig  2.10)
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 2.10 — Bi‑grams Extraction & Brand‑wise Comparison</strong></div>
  <img src="/assets/images/Fig2_10 Bi-grams extraction and brand-wise Comparisons.png" width="650">
</div>

For better visualisations, bigrams plot was also constructed (Fig  2.11a, 2.11b)
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 2.11a — Bigrams (Part A)</strong></div>
  <img src="/assets/images/Fig2_11a - Bigrams .png" width="650">
</div>

<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 2.11b — Bigrams Output (Part B)</strong></div>
  <img src="/assets/images/Fig2_11b - Bigrams Output.png" width="650">
</div>
The visualisations provide mixed signals, underscoring the need for modelling to derive more robust insights. To address this, we employed both LDA and BERTopic with transformer embeddings. These approaches complement each other: LDA captures the broader thematic structure or “big picture” (Yadav et al., 2025; Kushwaha & Kaur, 2025), while BERTopic provides greater contextual depth and detail (Grootendorst, 2022; EECSI, 2024).
  

## Chapter 3: Topic Modelling
## 3.1 Importing Libraries, Corpus and Vectorisation
Before applying topic modelling, the text data must be transformed into a numerical representation. 
We begin by importing the necessary libraries,  “gensim (Fig 3.1) “ “scikit-learn (Fig 3.2)” 
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 3.1 — Importing Gensim</strong></div>
  <img src="/assets/images/Fig3_1 - Importing Gensim.png" width="650">
</div>
 
Next, we vectorise the cleaned text using Bag of Words, filtering out overly common and rare terms (Fig 3.2). 
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 3.2 — Vectorisation</strong></div>
  <img src="/assets/images/Fig3_2 - Vectorisation.png" width="650">
</div>
 
Finally, we prepare a dictionary and corpus in the format required by Gensim’s LDA implementation (Fig  3.3). 

<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 3.3 — Importing Dictionary</strong></div>
  <img src="/assets/images/Fig3_3 - Importing Dict.png" width="650">
</div>
 
With the preprocessing complete,  I proceeded with modelling.

## 3.2 LDA Modelling 
## 3.2.1 Hyperparameter Tuning
Hyperparameter tuning of 5, 10 and 15 topics was performed  and 5 topics came up top at a Coherence score of  0.504 (Fig 3.4).
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 3.4 — Tuning & Coherence Score</strong></div>
  <img src="/assets/images/Fig3_4  - Tuning & Coherence Score.png" width="650">
</div>
 
Perplexity was also used to in the evaluation and the best (lowest) score was 15 topics of – 8.92 (Fig 3.5).
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 3.5 — Perplexity</strong></div>
  <img src="/assets/images/Fig3_5 Perplexity.png" width="650">
</div>
 
Perplexity favours more to less topics. In this case, Coherence takes precedence over Perplexity as research have shown that Coherence correlates with  better human interpretability (Chang et al., 2009; Stevens et al., 2012; Röder et al., 2015).

LDA was implemented with k=5 topics, which produced coherent and interpretable topics for this dataset. While it is technically possible to run an extended sweep (e.g., k =5 to k =20 ) to search for a mathematically optimal value, such exhaustive tuning is typically undertaken by beginners who rely solely on LDA for insight.

In this project, LDA serves as the breadth component, complemented by depth‑oriented modelling using BERTopic and transformer embeddings. Given this dual‑method architecture, additional LDA hyperparameter sweeps would offer diminishing returns and do not materially change the overall conclusions.

## 3.2.2 Comparison  of LDA’s 5 vs 10 topics 
As seen below the 10 topic is fragmented and contained overlapping themes like app usability, customer service, and brand mentions appear across several topic. This fragmentation reduces interpretability making the 5-topic more suitable
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 3.6 — 5 vs 10 Topics</strong></div>
  <img src="/assets/images/Fig3_6 - 5 vs 10 topics.png" width="650">
</div>
 

## 3.2.3 LDA topic Visulations (pyLDAvis) 

The selected 5‑topic LDA model was visualised using pyLDAvis.
Topic 1 (pyLDAvis indexing; equivalent to Topic 0 in the model) accounted for 28.9% of all tokens, making it the dominant topic.

The top relevant terms — order, customer, dont, time, day, get, return, service, shoe — indicate that this topic captures order fulfilment and customer‑service issues, consistent with earlier EDA findings (Fig 3.7)

 <div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 3.7 — pyLDAvis</strong></div>
  <img src="/assets/images/Fig3_7 -pyLDAvis.png" width="650">
</div>

## 3.2.4  Limitations of LDA

However, LDA is shallow and may miss contextual meaning because it relies on bag‑of‑words representations (Yilmaz, 2024). To complement LDA, BERTopic — which uses transformer‑based embeddings — was applied next.
 

## 3.3	BERTopic Modelling

BERTopic was instantiated using a SentenceTransformer model to generate contextual embeddings and a CountVectorizer for tokenisation. Default UMAP and HDBSCAN parameters were used unless otherwise stated. This configuration allows BERTopic to capture semantic similarity between reviews more effectively than LDA’s bag‑of‑words approach.

To complement the earlier LDA results, BERTopic was applied to uncover context‑rich, transformer‑based topics that may not be detectable through traditional probabilistic modelling

## 3.3.1	BERTopic Visualisation (Intertopic Map)

The BERTopic model produced several visual outputs that help interpret topic structure and semantic separation. The Intertopic Distance Map shows how topics are distributed in a two‑dimensional UMAP space, with larger circles indicating higher topic prevalence. The map demonstrates that BERTopic generates more distinct and semantically coherent clusters compared to LDA, reflecting the benefit of transformer‑based embeddings (Fig 3.8).
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 3.8 — BERT Intertopic Distance Map</strong></div>
  <img src="/assets/images/Fig3_8 - BERT Intertopic.png" width="650">
</div>
 
In addition, the Hierarchical Topic Tree illustrates how topics merge at different levels of granularity. This hierarchical structure is unique to BERTopic and provides insight into how related themes cluster together, such as usability issues, customer service concerns, and product quality feedback (Fig 3.9).
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 3.9 — Hierarchical Tree</strong></div>
  <img src="/assets/images/Fig3_9 - BERT Hierarchical Tree.png" width="650">
</div>
 
(Only the top portion of the hierarchy is shown due to the full tree’s length. The top-level merges illustrate how sematically related topics cluster together.)

Although the upper portion of the BERTopic hierarchy tree is dominated by repeated positive terms such as good, great, and love, this does not imply that positive sentiment dominates the dataset. This clustering occurs because BERTopic groups semantically similar embeddings at the highest level, and positive adjectives tend to be short, frequent, and lexically similar across brands. As a result, they merge early in the hierarchy due to their semantic proximity rather than their sentiment weight.

Where sentiment is concerned, dedicated sentiment analysis provides a more accurate representation of polarity distribution across brands. As shown earlier, the dataset contains substantial negative feedback despite the positive lexical cluster at the top of the hierarchy. The hierarchy tree therefore, reflects semantic similarity, not sentiment dominance.

As the tree branches downward, the model separates into more specific themes, including app usability issues, customer service concerns, and product‑related feedback. This hierarchical structure demonstrates how BERTopic captures both broad sentiment patterns and fine‑grained subtopics.

Together, these visualisations confirm that BERTopic identifies context‑rich, semantically meaningful topics that complement the earlier LDA results.

## 3.3.2	BERTopic Topic Interpretation
The BERTopic model generated X topics (after removing outliers), each represented by a set of semantically coherent key terms. Unlike LDA, which relies on bag‑of‑words co‑occurrence, BERTopic leverages transformer embeddings to capture contextual meaning. This results in topics that are more nuanced and better aligned with the underlying semantics of the reviews.

The table below summarises the key BERTopic topics and their representative terms. These topics reflect a mix of app‑related issues, customer service concerns, product quality feedback, and general shopping experience themes (Fig 3.10).
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 3.10 — BERTopic & Representative Terms</strong></div>
  <img src="/assets/images/Fig3_10 BERTopic & Rep Terms.png" width="650">
</div>
 

Across the topics, several patterns emerge:

• 	App Usability & Navigation: Topics containing terms such as easy use, navigate, quick, and interface reflect user experiences with app functionality and ease of use.

• 	Customer Service & Delivery: Topics with terms like service, delivery, refund, and support capture operational and service‑related feedback.

• 	Product Quality & Fit: Topics referencing fit, comfort, size, and quality relate to product‑specific evaluations ( appears in full BERTopic model; not in top 10)

• 	Promotions & Rewards: Topics containing discount, sale, points, and reward highlight user engagement with promotional mechanics( appears in full BERTopic model; not in top 10).

• 	Positive Experience Clusters: Several topics contain repeated positive expressions such as good, great, love, and amazing. These reflect general satisfaction but also contribute to the high‑level positive cluster observed in the hierarchy tree.

Compared to LDA, BERTopic produces more contextually distinct and semantically meaningful topics (Grootendorst, 2022; EECSI, 2024), particularly for app‑related and service‑related themes. This complements the earlier LDA results by providing deeper insight into the specific issues and experiences driving user feedback.

## 3.3.3	Brand-wise Topic Distribution

The brand‑wise topic distribution provides insight into how different themes are expressed across Nike, Adidas, Puma, and Gymshark. By mapping the BERTopic topics to each brand’s reviews, several patterns emerge (Fig 3.11):
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 3.11 — Brand‑wise Distribution</strong></div>
  <img src="/assets/images/Fig3_11 Brand Wise Distribution - Copy.png" width="650">
</div>
 
• 	Nike shows higher concentrations of topics related to refunds, returns, app crashes, and slow loading, indicating operational and technical frustrations.

• 	Adidas exhibits strong representation in brand‑affinity topics (e.g., “love adidas”), suggesting higher brand loyalty and positive sentiment.

• 	Puma displays a more balanced distribution across usability, delivery, and price‑related topics, reflecting a mix of functional and transactional feedback.

• 	Gymshark is dominated by positive experience topics, consistent with the sentiment analysis results showing overwhelmingly favourable reviews.

These patterns align closely with the earlier sentiment analysis, reinforcing the triangulated insight that Nike receives more negative operational feedback, while Adidas and Gymshark attract more positive brand‑driven responses. BERTopic therefore complements LDA by providing a more granular, context‑aware view of how each brand’s customer experience differs



## Chapter 4: Evaluation
## 4. Evaluation
This chapter consolidates the topic modelling outputs (LDA and BERTopic) into interpretable themes and examines how these themes are distributed across the four sportswear brands.

## 4.1 Semantic Labelling: Five Interpretable Themes
Across both LDA and BERTopic, five coherent themes consistently emerged:

## i.	App Usability & Navigation
Terms such as easy use, easy navigate, user friendly, and app easy reflect customer emphasis on smooth app interactions.

## ii.	Operational & Technical Issues
Topics containing login, crash, slow, payment, and update highlight recurring app reliability concerns.

## iii.	Delivery & Fulfilment
Words such as fast delivery, order, shipping, and time indicate that fulfilment processes are a major part of the customer experience.

## iv.	Price & Value Perception
Mentions of price high, great deal, and value show that customers are highly price‑aware and responsive to promotions.

## v.	Brand Affinity & Product Appeal
Phrases like love adidas, love puma, love nike, and good quality reflect strong emotional attachment and product satisfaction.
These themes form the basis for interpreting brand‑specific patterns (Fig 4.1).
<div style="text-align:center; margin-bottom: 1rem;">
  <img src="/assets/images/Fig4_1 - Mapping of Topic ID to Semantic Themes.png" width="650">
</div>

BERTopic naturally produced 10 micro‑topics because it clusters text at a more granular, sentence‑level resolution. However, for consistency and comparability with LDA — which produced 5 broader, keyword‑based topics — we collapsed BERTopic’s 10 micro‑topics into the same 5 macro‑themes. This ensures both models operate at the same conceptual level, making triangulation and interpretation clearer. The 10 BERTopic topics are shown for transparency and auditability, but the final analysis uses the collapsed 5‑theme structure.

## 4.2 Brand‑Wise Distribution
The brand‑wise topic distribution reveals how frequently each theme appears across Nike, Adidas, Puma, and Gymshark (Fig 4.2).
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 4.2 — Brand‑Wise Topic Distribution</strong></div>
  <img src="/assets/images/Fig4_2 - Brand Wise Distribution.png" width="650">
</div>
 

## Key observations:
• 	Nike, Adidas, and Puma show relatively similar distributions across the five themes.

• 	Gymshark, however, is heavily concentrated in App Experience and Brand Affinity topics, with fewer operational complaints.

• 	Nike shows higher representation in operational and technical issues.

• 	Adidas shows stronger presence in usability and brand‑affinity themes.

• 	Puma displays a balanced mix across all themes.

These differences suggest that each brand attracts a distinct customer profile with different expectations and pain points.

## 4.3 Implications: Market Share vs Operational Performance
The topic distribution patterns have several implications:
• 	Brands with larger review volumes (Nike, Adidas, Puma) naturally show more diverse topic representation, reflecting broader customer bases.

• 	Nike’s higher operational issue frequency may indicate friction points that could affect customer retention despite strong market presence.

• 	Adidas’s strong usability and brand‑affinity signals suggest a more positive app experience and stronger customer loyalty.

• 	Gymshark’s concentrated positive clusters align with its smaller but highly engaged community‑driven user base.

• 	Price‑related themes across all brands indicate that value perception remains a key competitive factor.

## Chapter 5: Recommendation and Analysis
## 5.1 Reply_Content Revisited
The dataset contains 6,011 missing replies out of 6,446 reviews, meaning 93.25% of all reviews received no developer response.
This indicates that developer engagement is generally low across the four brands (Fig 5.1).
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 5.1 — Reply Content Counts by Brand</strong></div>
  <img src="/assets/images/Fig5_1 - reply_content.png" width="650">
</div>
 

However, the non‑missing replies reveal a clear pattern:

• 	Gymshark is the only brand that consistently replies to users.

• 	Nike, Adidas, and Puma show almost no engagement, with replies appearing only as isolated exceptions.

This suggests that Gymshark adopts a more proactive approach to community interaction compared to the larger brands
## 5.2 Quality of Replies: Gymshark Personalised vs Adidas 
A qualitative scan of the reply texts shows two distinct styles (Fig 5.2):

## Gymshark
• 	Replies are personalised, conversational, and context‑specific.

• 	Tone is friendly and aligned with their community‑driven brand identity.

• 	Responses address the user’s issue directly.

## Adidas
• 	Replies are copy‑paste, generic, and repeated across multiple reviews.

• 	Example from your dataset:

“Thanks for your review. Latest version was mistakenly our internal testing build… Please update to the latest version.”

• 	This message appears 6 times, indicating a templated approach.
## Nike & Puma
• 	Almost no replies, suggesting minimal engagement (Fig.5.1).	
<div style="text-align:center; margin-bottom: 1rem;">
  <div><strong>Fig 5.2 — Sample Reply Content (Qualitative View)</strong></div>
  <img src="/assets/images/Fig5_2 - reply_content quali.png" width="650">
</div>
 
This contrast highlights how developer communication style varies significantly across brands.

## 6. Actionable UX Recommendations
This chapter translates the topic modelling insights into practical recommendations for improving the user experience (UX) across the four sportswear brands. The recommendations are grounded in the operational pain points surfaced in the topics and supported by established operations management principles.

## 6.1 Address Operational Pain Points: Inventory, Delivery, Customer Service

Topic modelling revealed recurring operational issues across Nike, Adidas, and Puma, particularly in:

• 	delivery delays

• 	order fulfilment errors

• 	inventory availability

• 	refund and return processes

These issues directly affect customer satisfaction because they occur at critical touchpoints in the purchase journey.
## Recommendations:

• 	Improve inventory visibility

Implement real‑time stock updates to reduce “item unavailable” or “cannot add to cart” complaints.

• 	Strengthen fulfilment reliability

Optimise last‑mile delivery partners and introduce proactive delivery notifications.

• 	Streamline customer service workflows

Reduce response times and automate triage for common issues (e.g., refund status, order tracking).
These improvements address the operational bottlenecks that surfaced repeatedly in LDA and BERTopic topics.

## 6.2 Enhance App & Experience Issues: Navigation, Sizing, Checkout, Reply Engagement
The topic models highlighted several UX‑specific issues:

• 	navigation difficulties (“not user friendly”, “hard to find”)

• 	checkout friction (“payment error”, “cant checkout”)

• 	sizing uncertainty (especially for apparel brands)

• 	low developer engagement (except Gymshark)

## Recommendations:

• 	Improve navigation pathways

Simplify menu structures and reduce the number of taps required to complete common tasks.

• 	Optimise checkout flow

Introduce error‑proofing, auto‑save carts, and alternative payment methods.

• 	Add sizing guidance

Use fit‑prediction tools or community‑sourced sizing feedback to reduce returns.

• 	Increase developer engagement

Adopt Gymshark’s personalised reply model to build trust and close the feedback loop.

These enhancements directly target the friction points identified in the topic clusters.

## 6.3 Grounding in Operations Management Principles

The recommendations align with established operations management frameworks:

• 	Heizer (2020) emphasises the importance of process reliability and service quality in shaping customer satisfaction.

• 	Slack (2022) highlights designing for flow, reducing variability, and managing bottlenecks.
Checkout errors, app crashes, and navigation issues represent UX bottlenecks that disrupt flow.

## 6.4 Strategic Takeaway: Recommendations Tied to Satisfaction Drivers

The strategic takeaway is clear:

Operational reliability + smooth app experience + responsive developer engagement = higher user satisfaction.

The  topic modelling results show that:

• 	operational issues generate the most friction

• 	app usability drives positive experiences

• 	developer replies reinforce trust and loyalty

Therefore, the brands should prioritise:

1. 	Fixing operational bottlenecks (delivery, inventory, refunds)
   
2. 	Improving app usability (navigation, checkout, sizing)
  
3. 	Strengthening engagement (personalised replies, faster response cycles)
   
These actions directly address the satisfaction drivers surfaced in your topic models and position the brands to improve both user experience and long‑term loyalty.
________________________________________
## 7. Limitations

While the topic modelling approach provides meaningful insights into customer experiences across the four sportswear brands, several limitations should be acknowledged to contextualise the findings.

## 7.1 Data Limitations

## Sparse Developer Replies

The “reply_content” field is 93.25% missing, which restricts the depth of analysis on developer engagement. Only Gymshark shows consistent replies, limiting cross‑brand comparison.

## Short Review Texts

Many reviews are extremely short (e.g., “great!”, “good app”), reducing the richness of semantic information available for topic extraction. Short texts can lead to:

• 	less stable topic assignments

• 	overlapping themes

• 	reduced interpretability

## Imbalanced Brand Representation

Adidas, Nike, and Puma have significantly more reviews than Gymshark. This imbalance may influence:

• 	topic frequency

• 	cluster density

• 	perceived brand‑level patterns

Gymshark’s concentrated topics may partly reflect smaller sample size.

## 7.2 Methodological Limitations

## LDA’s Bag‑of‑Words Constraints

LDA does not capture context or word order. As a result:

• 	semantically similar phrases may be split across topics

• 	nuanced meanings (e.g., “slow app” vs “slow delivery”) may be conflated

• 	topics may appear broader or more generic

## BERTopic Sensitivity to Parameters

Although BERTopic provides richer contextual embeddings, it is sensitive to:

• 	UMAP dimensionality reduction

• 	HDBSCAN clustering parameters

• 	random seed stability

Small parameter changes can produce different topic structures, affecting reproducibility.

## No Sentiment Modelling
This project covers Objective 1 only and  focuses solely on topic modelling.
Without sentiment analysis:
• 	topics cannot be directly linked to positive or negative experiences
• 	emotional intensity of themes remains unquantified
• 	satisfaction drivers must be inferred indirectly from topic content
This is consistent with the project scope but limits interpretive depth.

## 7.3 Interpretive Limitations
## Topics Reflect Frequency, Not Importance
Topic modelling identifies what users talk about most — not necessarily what matters most to them. High‑frequency themes (e.g., usability, delivery) may overshadow niche but critical issues.
## Ambiguity in Short Phrases
Single‑word or two‑word reviews can be ambiguous. For example:

• 	“good app”

• 	“nice”

• 	“bad”

These provide limited context, making topic assignment less precise.
## Brand‑Level Inference is Correlational

Differences in topic distribution across brands:

• 	reflect user discussions

• 	do not prove causal relationships

• 	may be influenced by brand size, user demographics, or marketing cycles

Interpretations should therefore be viewed as indicative rather than definitive.

## 7.4 Summary

These limitations do not undermine the value of the findings but highlight the need for cautious interpretation. Future work could incorporate sentiment analysis, richer metadata, or longitudinal tracking to strengthen the insights derived from topic modelling.

## 8. Conclusion

This project applied topic modelling (LDA and BERTopic) to 6,446 customer reviews across four sportswear brands to uncover the dominant themes shaping user experience. Five interpretable themes emerged consistently across both models: app usability, operational issues, delivery and fulfilment, price and value perception, and brand affinity.

Brand‑wise analysis showed that Nike, Adidas, and Puma share similar topic distributions, while Gymshark stands out with concentrated themes around app experience and community‑driven engagement. Developer replies, although sparse overall, revealed meaningful differences in communication style, with Gymshark providing personalised responses compared to the templated or absent replies from other brands.

The findings highlight that operational reliability, smooth app navigation, and responsive developer engagement are central drivers of user experience. These insights informed the UX recommendations in Chapter 6, which emphasise improving operational processes, enhancing app usability, and strengthening feedback loops.

Overall, topic modelling proved effective in extracting actionable insights from large‑scale textual data, offering a scalable approach for understanding customer needs and guiding UX improvements.


## 9. AI Ethics

## 9.1 Privacy
Given that app reviews can sometimes contain personal identifiers, the data was scraped from Google Play, where reviews are pre‑moderated by Google. This ensures compliance with Google Play’s terms and alignment with GDPR (EU) and PDPA (Singapore) standards. In addition, our team reviewed the dataset to confirm that no sensitive personal information was retained, thereby safeguarding user privacy during analysis.

## 9.2 Fairness
**Risk:** Bias in the dataset (e.g., reviews skewed toward certain brands, demographics, or regions) can lead to unfair insights.  

**Mitigation:** Balanced sampling is applied, limitations are documented, and results are not overgeneralised. Any bias or imbalances are acknowledged through **Analytical Limitations and Gaps** (see slide 47 PPT).

## 9.3 Accuracy
**Risk:** Machine Learning models may misclassify sentiment or context, leading to misleading recommendations.

**Mitigation:** Validate models with cross‑checks (e.g., LDA vs. BERTopic), and clearly state confidence levels and error margins.

## 9.4  Accountability
**Risk:** If insights are misused (e.g., companies act on flawed recommendations), responsibility can be unclear.

**Mitigation:** We maintain transparent documentation of methods, assumptions, and limitations. Team members take responsibility for their own ouput, all modelling choices were documented in scripts and slides for lecturers' review.

## 9.5 Transparency
**Risk:** Some machine learning models can be complex and difficult to interpret, which may obscure how decisions are made.  

**Mitigation:** We used interpretable models where possible (e.g., Naive Bayes, Decision Trees, Random Forest feature importance) and complemented them with explainable outputs such as topic modelling visualisations and labelled clusters. The rationale for model choices was documented to ensure clarity and lecturers' review.


## Source Codes and Datasets
## Data & Code Access
- [Dataset (CSV)](https://github.com/ApacheChief/sportswear-topic-modelling/blob/main/reviews.csv)
- [Topic Modelling Notebook](https://github.com/ApacheChief/sportswear-topic-modelling/blob/main/8903784Y_ITD_214_Project_TM.ipynb)
