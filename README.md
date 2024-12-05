Sunspots:  One interesting aspect of the Sun is its sunspots.  Sunspots are areas where the magnetic field is about 2,500 times stronger than Earth's, much higher than anywhere else on the Sun.  Because of the strong magnetic field, the magnetic pressure increases while the surrounding atmospheric pressure decreases.  This in turn lowers the temperature relative to its surroundings because the concentrated magnetic field inhibits the flow of hot, new gas from the Sun's interior to the surface. 

Sunspots tend to occur in pairs that have magnetic fields pointing in opposite directions.  A typical spot consists of a dark region called the umbra, surrounded by a lighter region known as the penumbra.   The sunspots appear relatively dark because the surrounding surface of the Sun (the photosphere) is about 10,000 degrees F (5,538 degrees C), while the umbra is about 6,300 degrees F (3482 degrees C).  Sunspots are quite large as an average size is about the same size as the Earth.

Sunspots, Solar Flares, Coronal Mass Ejections and their influence on Earth:  Coronal Mass EjectionCoronal Mass Ejections (shown left) and solar flares are extremely large explosions on the photosphere.  In just a few minutes, the flares heat to several million degrees F. and release as much energy as a billion megatons of TNT.  They occur near sunspots, usually at the dividing line between areas of oppositely directed magnetic fields.  Hot matter called plasma interacts with the magnetic field sending a burst of plasma up and away from the Sun in the form of a flare.  Solar flares emit x-rays and magnetic fields which bombard the Earth as geomagnetic storms.  If sunspots are active, more solar flares will result creating an increase in geomagnetic storm activity for Earth.  Therefore during sunspot maximums, the Earth will see an increase in the Northern and Southern Lights and a possible disruption in radio transmissions and power grids.  The storms can even change polarity in satellites which can damage sophisticated electronics.  Therefore scientists will often times preposition satellites to a different orientation to protect them from increased solar radiation when a strong solar flare or coronal mass ejection has occurred.

The Solar Cycle:  Sunspots increase and decrease through an average cycle of 11 years.  Dating back to 1749, we have experienced 23 full solar cycles where the number of sunspots have gone from a minimum, to a maximum and back to the next minimum, through approximate 11 year cycles.  We are now well into the 24th cycle.  This chart from the NASA/Marshall Space Flight Center shows the sunspot number prediction for solar cycle 24.  The NASA/Marshall Space Flight Center also shows the monthly averaged sunspot numbers based on the International Sunspot Number of all solar cycles dating back to 1750.  (Daily observations of sunspots began in 1749 at the Zurich, Switzerland observatory.) 

One interesting aspect of solar cycles is that the sun went through a period of near zero sunspot activity from about 1645 to 1715.  This period of sunspot minima is called the Maunder Minimum.  The "Little Ice Age" occurred over parts of Earth during the Maunder Minimum.  So how much does the solar output affect Earth's climate?  There is debate within the scientific community how much solar activity can, or does affect Earth's climate.  There is research which shows evidence that Earth's climate is sensitive to very weak changes in the Sun's energy output over time frames of 10s and 100s of years.  Times of maximum sunspot activity are associated with a very slight increase in the energy output from the sun.  Ultraviolet radiation increases dramatically during high sunspot activity, which can have a large effect on the Earth's atmosphere.  The converse is true during minimum sunspot activity.  But trying to filter the influence of the Sun's energy output and its effect on our climate with the "noise" created by a complex interaction between our atmosphere, land and oceans can be difficult.  For example, there is research which shows that the Maunder Minimum not only occurred during a time with a decided lack of sunspot activity, but also coincided with a multi-decade episode of large volcanic eruptions.  Large volcanic eruptions are known to hinder incoming solar radiation.  Finally, there is also evidence that some of the major ice ages Earth has experienced were caused by Earth being deviated from its average 23.5 degree tilt on its axis.  Indeed Earth has tilted anywhere from near 22 degrees to 24.5 degrees on its axis.  But overall when examining Earth on a global scale, and over long periods of time, it is certain that the solar energy output does have an affect on Earth's climate.  However there will always be a question to the degree of affect due to terrestrial and oceanic interactions on Earth. 

# sunspots
  ![image](https://github.com/user-attachments/assets/eff69ad7-e3b9-4337-a6a3-98b6adeff114)

Data description:
Daily total sunspot number derived by the formula: R= Ns + 10 * Ng, with Ns the number of spots and Ng the number of groups counted over the entire solar disk.

No daily data are provided before 1818 because daily observations become too sparse in earlier years. Therefore, R. Wolf only compiled monthly means and yearly means for all years before 1818.
![image](https://github.com/user-attachments/assets/9a6643c0-0c87-480f-8aea-da48c9588e5e)

In the TXT and CSV files, the missing values are marked by -1 (valid Sunspot Number are always positive).

New scale:
The conventional 0.6 Zürich scale factor is not used anymore and A. Wolfer (Wolf's successor) is now defining the scale of the entire series. This puts the Sunspot Number at the scale of raw modern counts, instead of reducing it to the level of early counts by R. Wolf.

![image](https://github.com/user-attachments/assets/a02d4ac3-4b40-46e7-a24a-5cf8f9157504)


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
![image](https://github.com/user-attachments/assets/fa9c999c-457e-468d-b24e-5258c82ddf6f)

Key Model Features:
Growth Models:
![image](https://github.com/user-attachments/assets/52bf22c6-a155-4d2a-8b7c-962fef605ad9)

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


