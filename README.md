# SolarInSight: Mapping the Path to Renewable Success in Germany’s Photovoltaic Landscape

## Project Overview

**SolarInSight** is a comprehensive analysis aimed at evaluating the potential for expanding photovoltaic (PV) systems across Germany. Collaborating with Google's Sunroof project, SolarInSight leverages diverse data sources to provide actionable insights for households, energy utility companies, and policymakers. The project focuses on assessing rooftop suitability, forecasting PV production, analyzing market factors, and understanding energy consumption patterns to support the energy transition towards renewable sources.

## Methodology

### Data Collection & Preparation

SolarInSight integrates data from five primary sources to create a robust dataset:

1. **Sunroof Data:**  
   - **Purpose:** Assessing PV capacity by analyzing rooftop suitability for solar panel installations using satellite imagery.
   - **Features:** Roof area, slope, orientation, and estimated potential energy generation.

2. **Weather Data:**  
   - **Labeled Training Data (Germany):** Used to train models predicting PV power output based on weather conditions.
   - **Unlabeled Weather Data (Germany):** Sourced from the Climate Data Center (CDC) to forecast PV production across various German locations.

3. **Electricity Prices:**  
   - **Focus:** Dynamic electricity prices from the Day-Ahead market to analyze cost-saving potentials.
   - **Data Source:** EnergyCharts, providing hourly auction prices and identifying market trends.

4. **Feed-in Tariffs:**  
   - **Objective:** Evaluating incentives for renewable energy through Germany's EEG-regulated feed-in tariffs.
   - **Data:** Monthly tariffs categorized by PV system capacity, focusing on partial feed-in systems.

5. **Electricity Consumption Data:**  
   - **Census Data Set:** Estimating energy demand based on household sizes and demographic information.
   - **Open Power System Data:** Hourly electricity consumption profiles from residential households and small businesses.

### Predictive Modeling

1. **Predicting Hourly Electricity Production:**  
   - **Models Used:** KNN, Random Forest, LGBM, XGBoost, Neural Networks.
   - **Approach:** Stacked ensemble combining Random Forest, LGBM, and XGBoost achieved the best performance (R² = 64.54%, RMSE = 4.24 W).

2. **Forecasting Hourly Electricity Prices:**  
   - **Technique:** ARIMA models trained using Google BigQuery Machine Learning to predict Day-Ahead auction prices.

3. **Simulation of Hourly Electricity Consumption:**  
   - **Method:** Gaussian Kernel Density Estimation (KDE) to simulate consumption patterns based on household demographics and census data.

4. **Development of Key Performance Indicators (KPIs) and Visualizations:**  
   - **Tools:** Looker Studio for creating dashboards that visualize annual savings, energy production, and CO₂ emissions across postal codes.

## Key Findings

- **Regional Savings Variations:**  
  Significant differences in potential annual savings across regions due to factors like weather conditions, rooftop capacity, and household energy consumption patterns.

- **Energy and Cost Optimization:**  
  Top 25% regions offer at least 26.6% higher potential annual savings, contributing to the generation of 159 million kWh of solar energy and reducing CO₂ emissions by 99.5 million kg.

- **Investment Efficiency:**  
  A 20% increase in electricity prices can shorten the break-even point for PV installations from 7.6 to 6 years, enhancing the economic viability of solar investments.

- **Dashboard Insights:**  
  The final dashboard provides detailed visualizations of annual savings per postal code, aiding stakeholders in identifying high-potential areas for PV system deployment.

## Conclusion

SolarInSight highlights the substantial potential for expanding PV systems in Germany by integrating diverse data sources to generate actionable insights. The project underscores the importance of data-driven decision-making in promoting renewable energy adoption and offers valuable guidance for stakeholders aiming to maximize the benefits of solar investments. While preliminary data provides promising results, the development of a robust data pipeline ensures readiness for integration with real-world data, enhancing future analyses and supporting the ongoing energy transition.
