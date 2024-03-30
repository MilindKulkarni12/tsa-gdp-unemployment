# Time Series Analysis of the U.S. GDP w.r.t. the Unemployment Rate
-   Forecast the GDP in USA by using Unemployment rate data and Leading Indicators of GDP data, and analyzing the relationship between GDP and Unemployment rate.
## Team Members
* Ayeshee Patra
* Milind Rajendra Kulkarni

## Datasets
* **Leading Indicators OECD: Reference Series: Gross Domestic Product (GDP):** ([USALORSGPNOSTSAM](https://fred.stlouisfed.org/series/USALORSGPNOSTSAM)) : This dataset provides a normalized GDP series for the United States, which is useful for analyzing trends and forecasting future economic conditions.
* **Unemployment Rate** ([UNRATE](https://fred.stlouisfed.org/series/UNRATE)): This dataset measures the percentage of the labor force that is unemployed and actively seeking employment.

The GDP and UNRATE dataset are inversely correlated, implying that if the GDP of the US grows then there is decrease in the number of unemployed people in the country. Subsequently, if the unemployment increases then the GDP goes down.

The GDP data is the target dataset while the UNRATE dataset acts as a covariate to the GDP data. This selection of UNRATE as covariate is based on the correlation factor between both the datasets. Ideal covariate behaves similarly or inversely to the data in the target series. 

## Steps performed
* **Data Filtering**: Filtered the null values from both the datasets and created dataframes for the overlapping period. 
* **Data Visualization**: Visualized both the datasets to get a feel of the data and identify any unusual spikes like during the COVID-19 period.
* **Correlation Analysis**: Correlation between Gross Domestic Product (GDP) and the Unemployment Rate to gain insights into economic dynamics of how the changes in unemployment impacts the GDP.  
	* There is a moderate negative linear relationship between the two variables. 
	* The negative sign indicates that as GDP increases, the unemployment rate tends to decrease, and vice versa.
* **Time Series Analysis**: Created time series for both the dataset. A
	* Decomposition Plot: Plot to understand the trend and seasonality in the data. 
	* ACF Plot: To understand the MA and AutoRegressive nature of the data.
	* PACF Plot: To understand the nature and degree of the autoregressive component of the data.
	* ADF Test: To identify the stationarity of the dataset.
* **Data Imputing**: Identified and smoothened the sudden spikes in data like the one during the COVID period so that it does not influence the overall model.
	* Identified the COVID period
	* Removed the data for that specific period
	* Applied Spline Fit method with appropriate smoothing parameter.
	* Imputed the forecasted values based on the smoothed fit model.
*  **Forecasting**: 
	* **regARIMA (AutoRegressive Integrated Moving Average)**: The regressive ARIMA helps us to forecast the target GDP series accurately with the covariate UNRATE series being used as the regressor.  
	* **VAR (Vector AutoRegressive)**: This model used for multivariate series where combinations of each parameter being a target and regressor for the other are analyzed to find the best fit model.

## Conclusion
Analyzed and forecast the relationship between the GDP and the Unemployment Rate in the United States.
