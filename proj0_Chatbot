## PROJECT: Detecting anomalous activity of a ship's engine

**Project description / Problem Statement:** A logistics company operates a fleet of ships. It needs an anomaly detection system for their fleet to prevent engine failures. Maintenance issues can cause safety risks, high costs, and delivery delays. By analyzing engine sensor data for early warnings, the goal is to implement proactive monitoring that ensures crew safety, reduces operational expenses, and protects revenue through timely corrective action.

---

### 1. Exploratory Data Analysis

A dataset of about 19,500 readings was used to track various features of the engine activity: engine RPMs, oil temperature and pressure, fuel pressure, etc. Each on its own does not point to an anomaly, but combinations of several abnormal readings might suggest potential issues. Histograms and boxplots of each feature helped to identify the distribution of the data and potential outliers. 

<img src="images/proj1/histograms2.png?raw=true"/>
<img src="images/proj1/boxplots.png?raw=true"/>

---

### 2. Methodology

Three methods were used to pinpoint outliers:
* Interquartile Range (IQR).
* One-Class Support Vector Machine (OC-SVM).
* Isolation Forest.

Principal Component Analysis (PCA) was used to reduce the dimensionality of the dataset and plot the various data points in 2D.

<img src="images/proj1/3_scatterplots_comparison.png?raw=true"/>

---

### 3. Results and Recommendations

The number of anomalies (outliers) common to all 3 methods, is summarised in the table underneath:

<img src="images/proj1/Anomalies.png?raw=true"/>

✔ The IQR method seemed the most appropriate for this dataset, since it is straight forward to
implement for a preliminary diagnostic of the Engine.

✔ If the Shipping company would prefer to fine-tune the analysis with smaller or larger proportions of samples, then Isolation Forest
would be the recommendation (more flexible than IQR).

✔ The selection of Isolation Forest (I.F.) vs. OC-SVM was based on lower complexity to implement (parameter tuning) and
because I.F. identified more common points with IQR than OC-SVM. This means more samples
with multi-feature outliers could be picked-up in comparison to OC-SVM.


For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

