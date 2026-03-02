## PROJECT: Create a "Feminist" Chatbot - MSc Dissertation

**Project description:** Interest in conversational agents (e.g. Amazon Alexa) and chatbots has increased significantly 
during recent years, motivated mainly by commercial benefits. However, with this rapid 
expansion, Artificial Intelligence (AI)-driven applications have also generated problems, some of them 
linked to gender bias and stereotypes detrimental to women. 
Despite years of progress made by Feminism since the 19th century, gender equality in many areas 
remains elusive. One of the most challenging issues concerns sexism in the workplace and in particular 
income inequality, also known as the gender pay gap (GPG). 
This MSc research project explored these topics. From the technical side, some of the latest AI and Machine 
Learning (ML) techniques were applied to create a prototype “Feminist Chatbot” called ABIE (Adviser 
for Better Income Equality). This meant that “Feminist Design Principles” guided the chatbot 
development, including a self-defence mechanism against sexist verbal abuse. The main purpose of the 
prototype was to increase awareness of the gender pay gap and to provide salary negotiation tips, 
especially for women. 


**NOTE:** this project was develpoed as part of an MSc in Computer Science at the University of Warwick (UK), completed in September 2021.
Nowadays more advanced chatbots have become widely established, after the initial release of ChatGPT in November 2022. While this project 
now might seem "behind the curve" in technical terms, the topics about bias in AI and the design principles remain valid even today.
More significantly, some of the fundamental architectural foundations (e.g. Transformers and NLP) also form part of the advanced AI-Chatbots.
It is also a matter of scale: vast amounts of data were used to train the models behind the advanced chatbots.
In contrast, for this preject a very small training dataset was used.

---

### 1. Initial Research

A dataset of about 19,500 readings was used to track various features of the engine activity: engine RPMs, oil temperature and pressure, fuel pressure, etc. Each on its own does not point to an anomaly, but combinations of several abnormal readings might suggest potential issues. Histograms and boxplots of each feature helped to identify the distribution of the data and potential outliers. 

<img src="images/proj1/histograms2.png?raw=true"/>
<img src="images/proj1/boxplots.png?raw=true"/>

---

### 2. Methodology

* Open source software was used to develop the chatbot, including Python and the development framework: Rasa (for rapid prototyping). 
* Natural Language Processing (NLP) capabilities were covered using the Transformer architecture, combined with the spaCy API.
* After cross-validation testing, the intial model average F1-Score of 0.928 for user intent classification. 
* Subsequently the chatbot (named "ABIE") was deployed to a cloud server using the Google Cloud Platform (GCP) to 
carry out a formative study.
* This was a small-scale academic study, so in total eleven test users (42% response rate) took part.
* Users were spread across various locations: the UK, Mexico and Singapore.
* The users were asked to interact with ABIE and afterwards complete an online survey to assess usability and user experience (UX).
  

---

### 3. Results and Conclusion

Results from the online survey:
* For **Usability**, the System Usability Scale (SUS) methodology was applied, resulting in a raw score of 67 (47% percentile rank), which was just under 
the industry benchmark of 68 for average usability (50% percentile).
* Due to small sample size and outliers, this result is merely indicative but already a good starting point for further development.
* The Short **User Experience** Questionnaire (UEQ-S) was integrated in the survey to evaluate UX.
* Participants judged the experience of chatting to ABIE as “positive” (UEQ-S score of 0.83), indicating it is already at a decent level of UX when compared to other benchmarks.
* Furthermore, the verbal abuse defense-mechanism was judged as “good” or “satisfactory” by a majority of users. 

These results illustrate how careful design and planning can ensure AI applications avoid spreading 
bias and harmful stereotypes. Moreover, such applications can also play an active role in advancing 
important social and ethical considerations, such as those related to gender equality.



For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
