# Kenya SPI-Analysis-2015-2025-Colab-Notebook

Kenya Precipitation Analysis and Standardized Precipitation Index (SPI) Monitoring developed using Google Earth Engine in a Google Colab notebook.

Overview
This repository contains a Google Colab notebook for analyzing historical and projected precipitation patterns in Kenya using the CHIRPS (Climate Hazards Group InfraRed Precipitation with Station data) dataset from Google Earth Engine. The analysis focuses on calculating the Standardized Precipitation Index (SPI) at multiple timescales (3-month, 6-month, and 12-month) to assess drought and wet conditions, along with visualizing monthly precipitation trends and spatial distribution.

Features
Data Acquisition: Accesses and processes precipitation data from the CHIRPS dataset via Google Earth Engine.
Monthly Precipitation Extraction: Extracts national average monthly precipitation for Kenya over an extended period (1981-2025).
Descriptive Statistics: Identifies months with the highest and lowest average precipitation, and analyzes monthly variability.
Standardized Precipitation Index (SPI) Calculation: Computes SPI-3, SPI-6, and SPI-12 using a Gamma distribution fitted to a baseline period (1981-2010).
Time Series Visualization: Plots monthly precipitation and SPI values over time, highlighting wet and dry periods.
Spatial Map Visualization: Displays annual total precipitation maps for selected years (e.g., 2015, 2020, 2022, 2025) using geemap.

Methodology
Define Spatial and Temporal Parameters: Sets the area of interest (Kenya boundary) and defines historical, baseline (1981-2010), and target (2015-2025) timeframes.
Earth Engine Data Processing: Utilizes the ee Python API to filter and sum CHIRPS precipitation data into monthly images.
Accumulated Rainfall Calculation: Computes rolling accumulated rainfall for 3, 6, and 12-month periods.
SPI Calculation: A custom Python function calculate_gamma_spi is used to:
Fit a Gamma distribution to the baseline monthly precipitation data.
Calculate the Cumulative Distribution Function (CDF) for target years' precipitation.
Transform CDF values into Standard Normal Distribution values (SPI).
Visualization: Employs matplotlib and seaborn for time series plots and bar charts, and geemap for interactive spatial maps.

Key Findings
Precipitation Seasonality: Identification of months with historically high (e.g., April) and low (e.g., February) average precipitation.
Variability: Analysis of monthly precipitation standard deviation, revealing periods of higher (e.g., November, April) or lower consistency (e.g., September).
Drought/Wet Periods: SPI plots clearly indicate periods of drought (negative SPI) and unusually wet conditions (positive SPI) at different timescales, providing insights into short-term (SPI-3) to long-term (SPI-12) hydrological impacts.
Spatial Anomalies: Visual maps showcase geographical distribution of total annual rainfall, aiding in identifying regional variations in precipitation.

Technologies Used
Google Earth Engine (EE)
geemap
pandas
numpy
scipy
matplotlib
seaborn

How to Run
Open in Google Colab: Click the "Open in Colab" badge (if available) or upload the .ipynb file to your Google Drive and open it with Colab.
Authenticate Earth Engine: Run the ee.Authenticate() cell and follow the instructions to authenticate your Google Earth Engine account.
Initialize Earth Engine: Run the ee.Initialize() cell.
Execute Cells: Run all cells in sequence. Ensure all required libraries are installed (Colab typically has these pre-installed).
