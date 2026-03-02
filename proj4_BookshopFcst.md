## PROJECT: Forecasting Book Sales for Independent Publishers

**Project description / Problem Statement:** Small to medium-sized independent publishers face significant financial risk due to high upfront costs
and unpredictable book lifespans. Unlike larger companies, these publishers lack the infrastructure to
leverage large-scale transactional data for strategic planning and forecasting. A market research agency specialising in tracking book sales
aims to develop a data-driven service that utilizes historical sales patterns and
seasonal trends. The goal is to provide actionable insights into long-term sales and economic life span,
enabling publishers to optimize their decision-making process.

---

### 1. Exploratory Data Analysis

The full dataset included UK weekly sales for several types of books, from January 2001 to July 2024. It included figures in volume (units sold) and value (in GBP).
The agency monitors physical, print book sales (not ebooks or audiobooks) via electronic point-of-sale systems, so online transactions are excluded.
For the study, the focus was on volume, i.e. to predict how many units would be sold at a given week. With the increase in online shopping, there has been a clear downward trend in physical sales:

<img src="images/proj4/AllSales.png?raw=true"/>


Asa proof-of-concept, the study focused on analyising sales of two books in different genres:
* "The Alchemist" (by P. Coehlo, adult, non-fiction)
* "The Very Hungry Caterpillar" (by E. Carle, Children's)

For the study, various models were trained on data from 2012 to 2023, then predictions obtained for the last 32 weeks, which were then assessed vs. the actuals in a "Test" subset. 

---

### 2. Methodology

The aim was to produce reasonable sales forecasts for each book separately. The approach was this:
* Data Preparation: extracted datasets and separated into training/testing (see below).

<img src="images/proj4/Train_Test.png?raw=true"/>

* Series Decomposition: used STL to assess trend, seasonality and residuals:
<img src="images/proj4/STL_Decomposition.png?raw=true"/>

* ACF, PACF and Stationarity: checked time-series stationarity assumptions.
* Auto-ARIMA: used the Pmdarima lybrary in Python to obtain the “best-fit” model (SARIMA); generated forecasts and compared vs. actuals.

<img src="images/proj4/SARIMA_Alchem.png?raw=true"/>

* XGBoost: created a XGBRegressor model, then generated forecasts and compared vs. actuals.
* LSTM: defined and trained a "baseline" stacked multi-step model, then used “KerasTuner” for hyperparameter tuning. Generated forecasts and compared vs. actuals.
* Hybrid: used the SARIMA model for volume predictions and combined with LSTM to model the residuals, then combined both to get a hybrid model and make predictions.
predictions of residuals, then compared total forecasts vs. actuals.
* Monthly Modelling: explored the option of aggregating weekly figures into monthly, then developed XGBoost and SARIMA models to compare vs actuals and vs. the weekly models.


---

### 3. Results and Recommendations

Outcome: number of anomalies (outliers) common to all 3 methods, summarised in this table:

<img src="images/proj1/Anomalies.png?raw=true"/>


### 4. Provide a basis for further data collection through surveys or experiments

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. 

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
