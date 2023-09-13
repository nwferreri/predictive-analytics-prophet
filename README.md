# Predictive Analytics - Facebook Prophet

## Goal

We want to be able to predict the demand for shelter in New York City for the next month.

## Data

Time-series data covering 366 weeks from 1/5/2014 to 1/3/2021. Includes the recorded number of individuals in shelters and temperature for each week. Also includes indicators if Easter, Thanksgiving, or Christmas occurred during that week.

## Analysis

For the Prophet model, it was decided that Easter and Thanksgiving would be treated as holidays, with Christmas treated as an additional regressor.

The data was cleaned and split into training and test sets. The test set spanned the final 4 weeks of the data.

The initial model was run and evaluated using mean absolute error (MAE) and root mean squared error (RMSE).

Parameter tuning with cross-validation was performed to improve the model. Best parameters were selected based on RMSE.

A final model was run using the best parameters, but yielded minimal improvements over initial model.

## Insights

The following figure visualizes the model:<br>
![image](https://github.com/nwferreri/predictive-analytics-prophet/assets/112211174/e214fe9f-79cf-4fe6-97a8-9bad9c29101d)<br>
Black dots are data, blue line is model prediction, light blue show error bounds.

Time-series components were also plotted:<br>
![image](https://github.com/nwferreri/predictive-analytics-prophet/assets/112211174/7a264853-7875-47b9-bd8e-70f8a941bcde)<br>

* Trend: there has been a decrease in shelter demand since mid 2019.
* Holidays: Easter and Thanksgiving have relatively small impacts on shelter demand.
* Yearly seasonality: well definied pattern that peaks in colder months and drops in warmer months.
* Christmas: relatively small fluctuations
