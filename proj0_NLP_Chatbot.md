## PROJECT: Create a "Feminist" Chatbot - MSc Dissertation

**Project description:** Interest in conversational agents (e.g. Amazon Alexa) and chatbots has increased significantly 
recently. However, with this rapid expansion, AI-driven applications have also generated problems, some of them 
linked to gender bias and detrimental stereotypes. 
This MSc research project explored these topics. From the technical side, some of the latest AI and Machine 
Learning (ML) techniques were applied to create a prototype “Feminist Chatbot” called ABIE (Adviser 
for Better Income Equality). 
This meant that “Feminist Design Principles” guided the chatbot 
development. The main purpose of the chatbot was to increase awareness of the gender pay gap. 


**NOTE:** this project was developed as part of an MSc in Computer Science at the University of Warwick (UK), completed in September 2021.
Nowadays more advanced chatbots have become widely established, after the initial release of ChatGPT in November 2022.
While this now might seem technically "behind the curve", the topics about bias in AI and fair design principles remain valid today.
Moreover, some of the fundamental architectural blocks (e.g. Transformers) still play a role in more advanced chatbots.

---

### 1. Initial Research:
* Researched development of chatbots from early stages (ELIZA, PARRY) to more recent examples (IKEA chatbot, Siri, etc).
* Conducted literature research to identify main problems with bias and detrimental gender stereotypes embedded in chatbots.
* Investigated the latest developments in AI and Machine Learning to use with chatbots, e.g. NLP and the Transformer architecture.
* Explored different frameworks for chatbot rapid-prototyping, e.g. RASA. 
* Agreed the requirements for the application using the MoSCow prioritisation technique.
* Selected the most relevant tools for assessing Usability and UX.
 

---

### 2. Methodology

* Open source software was used to develop the chatbot, including Python and the development framework: RASA (for rapid prototyping). 
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
* For **Usability**: the System Usability Scale (SUS) methodology was applied, resulting in a score of 67 (47% percentile rank), which was just under 
the industry benchmark of 68 for average usability (50% percentile).
* Due to small sample size and outliers, this result is merely indicative but already a good starting point for further development.
* The Short **User Experience Questionnaire** (UEQ-S) was integrated in the survey to evaluate UX.
* Participants judged the experience of chatting to ABIE as “positive” (UEQ-S score of 0.83), indicating it is already at a decent level of UX when compared to other benchmarks.
* Furthermore, the verbal abuse defense-mechanism was judged as “good” or “satisfactory” by a majority of users. 

These results illustrate how careful design and planning can ensure AI applications avoid spreading 
bias and harmful stereotypes. Moreover, such applications can also play an active role in advancing 
important social and ethical considerations, such as those related to gender equality.



For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
