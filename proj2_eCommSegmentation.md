## PROJECT: Customer Segmentation for an e-Commerce Business

**Project description / Problem Statement:** The client is an e-Commerce company who wants to understand various segments within its customer
base. By clustering customers based with similar characteristics and behaviours (e.g. age, shopping
frequency, spend value, etc.), the client could design different marketing campaigns with various goals: retention, win-back, up-selling, etc.

---

### 1. Exploratory Data Analysis

The initial dataset contained 951,669 records, with 20 columns (features). It was necessary to pre-process it (aggregate data) for the
analysis. There were 5 features considered relevant for creating meaningful clusters:

● A. Frequency: How often a customer buys over a given period.
● B. Recency: How recently a customer made a purchase or placed an order.
● C. Customer-Lifetime-Value (CLV): Total value (revenue) a customer contributes.
● D. Average Unit Cost: Indicates if a customer prefers high- or low-value items (on average).
● E. Customer Age. 

Boxplots of the processed dataset revealed outliers in 4 of the 5 features (not with customer age).

<img src="images/proj2/EDA_boxplots.png?raw=true"/>

---

### 2. Methodology

Three methods were used to estimate the "ideal" number of clusters to apply, below the outcome of each:
● Elbow Method: 5 to 10 clusters.
● Silhouette Score: 2 to 6.
● Hierarchical Clustering: 3 to 6.

Below is the dendrogram from the hierarchical approach:
<img src="images/proj2/dendrogram.png?raw=true"/>

Based on these overlapping numbers, the "optimal" number chosen was k=5 clusters (deciding factor was the highest average value of the Silhoutte score).

The K-Means Clustering algorithm was then applied, and the results visualised in 2D using Principal Component Analysis (PCA) and t-distributed Stochastic Neighbor Embedding (t-SNE). The t-SNE plot is shown below:

<img src="images/proj2/Clusters-tSNE.png?raw=true"/>

 
---

### 3. Results and Recommendations

Based on the feature characteristics for each cluster, an overall description for each can be defined and is presented in the table below. The e-Commerce business could then tailor specific marketing campaigns to target each customer segment accordingly, e.g. specific advertising for high-end/high-value items for cluster 3, etc.

<img src="images/proj2/Clusters_Table.jpg?raw=true"/>
 
For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
