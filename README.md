# natgas-model

- See output/clean_dataset.csv for full, clean dataset to conduct your own anaylsis

This is a project that seeks to analyse the US natural gas market by collating data on all of the follwing:

- Commitment of traders (via https://www.cftc.gov/MarketReports/CommitmentsofTraders/HistoricalCompressed/index.htm)
- US real GDP (via https://www.spglobal.com/marketintelligence/en/mi/products/us-monthly-gdp-index.html)
- US population (via https://fred.stlouisfed.org/series/POPTHM)
- US temperatures (via meteostat library) - pip install meteostat

--------------------------
https://www.eia.gov/naturalgas/data.php
- Natural gas production
- Natural gas consumption
- Natural gas storage
- Natural gas imports
- Natural gas exports
- Nautral gas price
--------------------------

To get required data you must:
- Download all of the datasets above on a monthly timeframe where available and import into dataframes(converting to monthly if only available in higher resoloution).
- Install and use meteostat library to find monthly historical temperatures within specified US cities stored in dataframes (then calculate heating degree days and cooling degree days from this).

This will then allow you to conduct basic analysis of this data.

To conduct the regressions in the same fashion you must:
- Merge all dataframes and export as a CSV
- Import the CSV into Stata
- Create natural log values for every varaible with command (gen ln_var_name = ln(var_name)) where var_name is the name of the individual variable
- Then conduct linear regression with command - (regress y, x1, x2, x3...)
(Alternatively conduct regressions in your preferred way)
