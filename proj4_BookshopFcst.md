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

It is important to mention there were three COVID-19 lockdowns in the UK in 2020 and 2021, when no physical sales took place. These "shocks" had a significant impact on the
patterns seen until then and thus influenced the structure of the data.

As a proof-of-concept, the study focused on analyising sales of two books in different genres:
* "The Alchemist" (by P. Coelho, adult-fiction)
* "The Very Hungry Caterpillar" (by E. Carle, Children's)

For the study, various models were trained on data from 2012 to 2023, then predictions obtained for the last 32 weeks, which were evaluated vs. actuals. 

---

### 2. Methodology

The aim was to produce reasonable sales forecasts for each book separately. The approach was this:
* **Data Preparation**: extracted data for each book and separated into training/testing (see below).

<img src="images/proj4/Train_Test.png?raw=true"/>

* **Series Decomposition**: used STL to assess trend, seasonality and residuals:
<img src="images/proj4/STL_Decomposition.png?raw=true"/>

* **ACF, PACF and Stationarity**: checked time-series stationarity assumptions.
* **Auto-ARIMA**: used the Pmdarima library in Python to obtain the “best-fit” model (SARIMA); generated forecasts and compared vs. actuals.

<img src="images/proj4/SARIMA_Alchem.png?raw=true"/>

* **XGBoost**: created a XGBRegressor model, then generated forecasts and compared vs. actuals.
* **LSTM**: defined and trained a "baseline" stacked multi-step model, then used “KerasTuner” for hyperparameter tuning. Generated forecasts and compared vs. actuals.
* **Hybrid**: used SARIMA to predict trend and seasonality; LSTM to model and predict residuals. The hybrid predictions were then compared to actuals.
* **Monthly Modelling**: explored the option of aggregating weekly figures into monthly, then developed XGBoost and SARIMA models to compare vs actuals and vs. the weekly models.


---

### 3. Results and Recommendations

To compare forecasts vs. actuals, two key metrics were used: Mean Absolute Error (MAE) and Mean Percentage Absolute Error (MAPE).
MAE is relevant when comparing models using the weekly data. For comparisons between weekly and monthly, using MAPE makes more sense.
Overall, the weekly predictions had better performance than the monthly ones, below a summary (only comparing XGBoost and SARIMA):

<img src="images/proj4/Metrics.png?raw=true"/>

Among the weekly models, for "The Alchemist" the best performance was with XGBoost (MAE: 118.8, MAPE: 0.19),
whereas for "The Caterpillar" the SARIMA model performed best (MAE: 357.8 , MAPE: 0.19).

Time series plots showing the predictions with a 95% confidence interval for each book are illustrated below.

<img src="images/proj4/Final_Alchem_XBG.png?raw=true"/>
<img src="images/proj4/Final_Caterpillar_SARIMA.png?raw=true"/>


Practical recommendations for small-medium independent publishers:
* **1. Keep Weekly Level**: Monthly aggregation does not improve accuracy. From a business perspective, weekly forecasting
offers better flexibility for inventory management and reduces the financial risks associated with
committing to month-long stock levels
* **2. Be flexible and ready to adapt**: Different target audiences create distinct book sales profiles.
Because model performance varied significantly, publishers should adapt their forecasting techniques to the specific dataset
rather than applying a universal solution.
* **3. High accuracy with real-life data is a challenge**: External shocks, such as COVID-19 lockdowns, demonstrate how easily models can be disrupted.
With an estimated error of approximately 19%, clients must account for this margin of uncertainty and recalibrate regularly to correct for deviations.
* **4. Benefit from a strong starting point**: While not perfect, these models provide a good starting point for anticipating volatility and seasonal trends.
These models allow publishers to draft preliminary strategies tailored to specific book genres, while remaining mindful of inherent market risks


For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
