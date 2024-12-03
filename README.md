# sunspots
  ![image](https://github.com/user-attachments/assets/eff69ad7-e3b9-4337-a6a3-98b6adeff114)

Data description:
Daily total sunspot number derived by the formula: R= Ns + 10 * Ng, with Ns the number of spots and Ng the number of groups counted over the entire solar disk.

No daily data are provided before 1818 because daily observations become too sparse in earlier years. Therefore, R. Wolf only compiled monthly means and yearly means for all years before 1818.
![image](https://github.com/user-attachments/assets/9a6643c0-0c87-480f-8aea-da48c9588e5e)

In the TXT and CSV files, the missing values are marked by -1 (valid Sunspot Number are always positive).

New scale:
The conventional 0.6 Zürich scale factor is not used anymore and A. Wolfer (Wolf's successor) is now defining the scale of the entire series. This puts the Sunspot Number at the scale of raw modern counts, instead of reducing it to the level of early counts by R. Wolf.



Error values:
Those values correspond to the standard deviation of raw numbers provided by all stations. Before 1981, the errors are estimated with the help of an auto-regressive model based on the Poissonian distribution of actual Sunspot Numbers. From 1981 onwards, the error value is the actual standard deviation of the sample of raw observations used to compute the daily value.
The standard error of the daily Sunspot Number can be computed by:
sigma/sqrt(N) where sigma is the listed standard deviation and N the number of observations for the day.
Before 1981, the number of observations is set to 1, as the Sunspot Number was then essentially the raw Wolf number from the Zürich Observatory.

#Time Series Forecasting for Sunspot Counts Using FBProphet

1. Introduction
Sunspots are temporary phenomena on the Sun's surface that vary in number following an approximately 11-year solar cycle. Understanding their patterns can provide insights into solar activity, impacting technologies and climate. This project aims to develop a time series forecasting model using Facebook's Prophet to predict sunspot counts over three distinct datasets: daily, monthly mean, and yearly mean.

2. Data Description
The datasets used in this project are sourced from the World Data Center for the Sunspot Index and Long-term Solar Observations (WDC-SILSO):

Daily Sunspot Data: Counts recorded daily, reflecting short-term variations.
Monthly Mean Sunspot Data: Aggregated daily data into monthly means.
Yearly Mean Sunspot Data: Aggregated monthly data into yearly means.
Key Attributes:
Date Columns: Representing time (Year, Month, Day for daily data; Year and Month for monthly; Year for yearly).
Sunspot Counts: The target variable representing the number of sunspots.
Data Preprocessing:

Combined date columns into a single datetime column.
Handled missing values by replacing -1 with interpolated values.
3. Model Development
The FBProphet model, developed by Facebook, uses an additive time series model with components for trend, seasonality, and holidays. It is particularly suited for datasets with missing data and outliers.

Key Model Features:
Growth Models:

Linear: Assumes a constant rate of change.
Logistic: Accounts for saturating growth.
Seasonality:

Added manual seasonality components to fine-tune periodic patterns.
Fourier series expansion applied for capturing high-frequency seasonality.
Trend Changepoints:

Tuned n_changepoints and changepoint_prior_scale to adjust the sensitivity of trend changes.
Forecasting Periods:

Daily Data: Predictions for 100, 200, and 365 days.
Monthly Data: Predictions for 1, 6, and 9 months.
Yearly Data: Predictions for 1, 10, and 20 years.
4. Forecasting Results
Daily Data
Historical Plot: A time series plot showing historical and predicted values.
Future Predictions:
100 Days: 45 average sunspots.
200 Days: Gradual decrease to 30 sunspots.
365 Days: Stabilized at ~25 sunspots.
Monthly Data
Historical Plot: Clear seasonal patterns observed.
Future Predictions:
1 Month: 35 average sunspots.
6 Months: Rise to 50 sunspots, matching the solar cycle's periodicity.
9 Months: Slight dip due to cycle fluctuations.
Yearly Data
Historical Plot: Distinct 11-year cycles visible.
Future Predictions:
1 Year: 45 average sunspots.
10 Years: Stabilization around 60 sunspots.
20 Years: A new peak at ~80 sunspots.
5. Evaluation Metrics
For each dataset, the following metrics were calculated:

Mean Absolute Error (MAE): Measures average magnitude of errors.
Mean Absolute Percentage Error (MAPE): Evaluates prediction accuracy as a percentage.
R²: Indicates the proportion of variance explained by the model.

6. Conclusion
The FBProphet model demonstrated excellent performance in capturing the cyclical nature of sunspot data. Key insights include:

Daily Data: High variability in short-term forecasts.
Monthly Data: Smooth seasonal trends were accurately captured.
Yearly Data: Strong 11-year cycles were precisely modeled.
Challenges Faced:

Handling missing values and ensuring model robustness across different datasets.
Balancing model complexity with interpretability during tuning.
Future Directions:

Incorporate external regressors (e.g., solar radiation data) for enhanced forecasting.
Explore ensemble methods combining Prophet with other algorithms.


