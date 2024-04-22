# natgas-model

- See output/clean_dataset.csv for full, clean dataset to conduct your own analysis

This is a project that seeks to analyse the US natural gas market by collating data on all of the following:

- Commitment of traders (via https://www.cftc.gov/MarketReports/CommitmentsofTraders/HistoricalCompressed/index.htm)
- US real GDP (via https://www.spglobal.com/marketintelligence/en/mi/products/us-monthly-gdp-index.html)
- US population (via https://fred.stlouisfed.org/series/POPTHM)
- US temperatures (via meteostat library) - pip install meteostat

AND
- Natural gas production
- Natural gas consumption
- Natural gas storage
- Natural gas imports
- Natural gas exports
- Natural gas price
ALL FROM (https://www.eia.gov/naturalgas/data.php)

----------------------------------------------------------

To get the required data you must:
- Download all of the datasets above on a monthly timeframe where available and import them into data frames (converting to monthly if only available in higher resolution).
- Install and use the meteostat library to find monthly historical temperatures within specified US cities stored in dataframes (then calculate heating degree days and cooling degree days from this).

This will then allow you to conduct a basic analysis of this data.

To conduct the regressions in the same fashion you must:
- Merge all data frames and export as a CSV
- Import the CSV into Stata (or optionally use python)
- Create natural log values for every variable with the command (gen ln_var_name = ln(var_name)) where var_name is the name of the individual variable (or do python alternative with dataframes)
- Then conduct linear regression with command - regress y, x1, x2, x3... (or python alternative with library)
(Alternatively, conduct regressions in your preferred way)
