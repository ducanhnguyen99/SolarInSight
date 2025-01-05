Introduction
The notebooks represent a complete pipeline to run the analysis and extract the insights and relevant data for visualization of the potential of PV panels in Germany. Many (intermediate) results are saved in BigQuery Tables due to the properties of the large dataset. If needed, please contact one of us to grant access. [carolinflosdorf@gmail.com ducanh.vdan@gmail.com zoe.zantow@gmail.com]

Running the pipeline:
The notebooks generate BigQuery Tables that are used in a consecutive step. Therefore, the order of execution of notebooks is important.
1.	Postal_code_polygon_germany.ipynb
2.	Electricity_price_and_weather_forecasting.ipynb (Execution time ~ 6 hours)
3.	Electricity_production_prediction.ipynb
4.	Electricity_consumption_simulation.ipynb (Execution time ~ 15 hours)
5.	Main_insights.ipynb

The BigQuery Tables are then saved at the corresponding location indicated in the notebook description. Looker Studio allows to easily exchange these datasets in the visualization by simply updating the BigQuery Table in the already existing Looker Site by adding the new data source and selecting it. 
For the interactive map: results.savings_plz2, results.savings_plz5
For the insights: results.experiment_kpis, results.varying_feed_in_tariff

The interactive dashboard can be viewed at: 
https://lookerstudio.google.com/reporting/fe012bf7-d611-4bfd-881b-575b9746710c

Google Drive Link to notebooks:
https://drive.google.com/drive/folders/1utAMhFF9M834-i2XKRN9a4o768gcqFHS?usp=sharing

Jupyter Notebooks:
Postal_code_polygon_germany.ipynb
-	used to map geography polygons to postal code areas for mapping between dimensions and to use geospatial functions
o	saved in BigQuery table: geo_data.plz5_polygone, geo_data.plz2_polygone

Electricity_price_and_weather_forecasting.ipynb
-	forecasts electricity prices using ARIMA Models, starting from 02.06.2023 0:00 on 10000 values are forecast
o	any date in the future can be continuously forecasted in case of analyzing a different timeframe 
o	saved in BigQuery table: electricity_data.day_ahead_auktion_forecast_data
-	Forecasts weather using ARIMA Models for the electricity production prediction
o	saved in BigQuery table: electricity_production_data.weather_forecast_data
-	Calculates weighted average of feed-in price of electricity
Electricity_production_prediction.ipynb
-	predicts electricity production of one cell using different regression models, based on the forecasted weather 
o	saved in table: electricity_production_data.predicted_power_output_minimal
Electricity_consumption_simulation.ipynb
-	simulates electricity consumption of postal code areas using gaussian KDE and conditional probability distributions
-	Simulation runs for over 15 hours in total – can be set to run iteratively picking up from the last point simulated, instructions in comments at “Run Simulation” subsection
-	different 1 year timeframe to simulate can be set using original_date in the subsection “Run Simulation” 
o	saved in BigQuery table: geo_data.postal_code_consumption
Main_insights.ipynb
-	combines consumption, production and prices to estimate potential savings per postal code area
o	saved in BigQuery table: results.hourly_savings
-	Maps savings onto postal code polygons
o	saved in BigQuery table: results.savings_plz2, results.savings_plz5
-	Calculates Insights and Impact of the analysis
o	saved in BigQuery table: results.experiment_kpis, results.varying_feed_in_tariff
