# natgas-model
This is a project that seeks to analyse the US natural gas market by collating data on all of the following:

# Data
- Commitment of traders (via https://www.cftc.gov/MarketReports/CommitmentsofTraders/HistoricalCompressed/index.htm)
- US real GDP (via https://www.spglobal.com/marketintelligence/en/mi/products/us-monthly-gdp-index.html)
- US population (via https://fred.stlouisfed.org/series/POPTHM)
- US temperatures (via meteostat library) - pip install meteostat

AND BELOW FROM (https://www.eia.gov/naturalgas/data.php)
- Natural gas production
- Natural gas consumption
- Natural gas storage
- Natural gas imports
- Natural gas exports
- Natural gas price

----------------------------------------------------------

# Cleaning

To get the required data you must:
- Download all of the datasets above on a monthly timeframe where available and import them into data frames (converting to monthly if only available in higher resolution).
- Install and use the meteostat library to find monthly historical temperatures within specified US cities stored in dataframes (then calculate heating degree days and cooling degree days from this).

This will then allow you to conduct a basic analysis of this data.

To conduct the regressions in the same fashion in STATA you must:
- Merge all data frames and export as a CSV
- Import the CSV into Stata 
- Create natural log values for every variable with the command (gen ln_var_name = ln(var_name)) where var_name is the name of the individual variable 
- Then conduct linear regression with command - regress y, x1, x2, x3... 

Alternatively to conduct regression in Python use your own desired method or see python_regression.jpynb

- See output/clean_dataset.csv for full, clean dataset to conduct your own analysis

----------------------------------------------------------
# Required Libraries
- numpy
- matplotlib.pyplot
- matplotlib.dates
- pandas
- datetime
- warnings
- statsmodels.api
- meteostat