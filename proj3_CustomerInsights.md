## PROJECT: Extracting insights from online Customer Reviews for a Fitness/Gym Business

**Project description / Problem Statement:** A market leader in the fitness sector would like to keep its competitive edge by deeply understanding their club members' motivations and behaviours.
They have a need to leverage innovative technology to refine the customer experience without compromising the core value proposition. This project addresses the challenge of identifying specific
drivers of member satisfaction by analysing online review data (Google Reviews and Trustpilot) to provide actionable insights that improve the overall customer experience.

---

### 1. Exploratory Data Analysis

The datasets included 11,879 reviews from Google and 16,581 from Trustpilot (in English), spanning March 2022 to May 2024. The analysis identified 310 locations common in both sets, pin-pointing the "top 30"
problem sites (negative reviews). Word frequency analysis showed that while overall reviews included terms like "friendly" and "clean", negative feedback focused on infrastructure and service issues.
The corresponding word-cloud and word-frequency histogram for all negative reviews are below:  

<img src="images/proj3/WordCloud_All Negatives.png?raw=true"/>
<img src="images/proj3/WordFrequency_All Negatives.png?raw=true"/>

---

### 2. Methodology

This multi-staged analytical framework was employed to process the data and extract insights:
* Data Preparation: Datasets were cleaned and pre-processed.
* Sentiment and Word-Frequency Analysis: Reviews were filtered to isolate negative reviews (scores below 3). Word-frequency analysis was conducted to identify recurring themes.
* Initial Topic Modelling: Used BERTopic (a modular, transformer-based topic modelling library ) to identify topic clusters within the negative reviews. The top 8 clusters are below:
<img src="images/proj3/Bertopic_All_Negatives.png?raw=true"/>

* Top 30 Locations Analysis: Aggregated the review counts to find the sites with highest number of negative reviews. Applied BERTopic to this subset.
* Emotion Analysis: Used a BERT-based model from Hugging-Face to extract the top “emotion” from each negative review: "Anger" was the highest overall (see below).
<img src="images/proj3/Emotions_Distribution.png?raw=true"/>

* Deep-dive into "angry" reviews: BERTopic was then applied to this subset of reviews to understand specific drivers of high-intensity dissatisfaction.
* Topic Modelling using a Large-Language-Model (LLM): Loaded the Phi-4 model from Hugging Face. A prompt was utilized to extract top 3 topics from the dataset (Top-30 locations), which generated a hierarchical view of clusters (see below)
  <img src="images/proj3/Bertopic_LLM_Dendrogram.png?raw=true"/>
  
* Latent Dirichlet Allocation (LDA) Model: used this to perform topic modelling on the negative reviews (all locations) to provide a comparative baseline, below a cluster example.
<img src="images/proj3/LDA_Topics_Vis.png?raw=true"/>
  
* Synthesis and Recommendation: Consolidated findings from all stages, identifying core systemic issues and formulated evidence-based recommendations for the client.


---

### 3. Results and Recommendations
A map showing the top 20 sites with highest number of negative reviews was generated, so these could be prioritised for further investigation and targeted action. 
The relative size of each site "marker" was proportional to the number of negative reviews (i.e. the bigger the circle the more negatives).
For data protection reasons, the actual map is not shown here, but an example (unrelated) of the visualisation is below:
<img src="images/proj3/MapExample.jpg?raw=true"/>


Based on all the insights from the analysis, a list of 10 actionable recommendations was generated, aiming to address the most recurrent topics from the customer reviews:

<img src="images/proj3/Recommendations.jpg?raw=true"/>


For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
