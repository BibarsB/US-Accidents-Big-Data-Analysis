# US Accidents Big Data Analysis

A university Big Data Analytics & Visualization project analyzing the US Accidents dataset using Polars, PySpark, Spark MLlib, Plotly, and Dash.

The project explores patterns in reported US traffic accidents across time, location, weather conditions, road features, and geographic regions.

## Project Overview

The original dataset contains more than 7.7 million accident records from 2016 to March 2023.

To create a reproducible and manageable analytical workflow, the project uses a 20% severity-stratified sample while preserving the original Severity distribution.

After preprocessing and validation, the final dataset contains:

- 1,538,632 processed accident records
- 18 selected source columns
- additional engineered features for time, duration, weather, and location

## Main Workflow

The notebook follows a step-by-step pipeline:

1. Setup and environment configuration
2. Data loading
3. Data quality checks
4. Severity-stratified sampling
5. Data preprocessing
6. Feature engineering
7. Validation
8. Aggregation and analysis
9. Interactive visualizations
10. PySpark K-Means geographic clustering
11. Dash dashboard
12. Findings and limitations

## Technologies Used

- Python
- Polars
- PySpark
- Spark MLlib
- Parquet
- Plotly
- Dash

## Feature Engineering

Several features were created to support the analysis, including:

- Accident duration
- Year
- Month
- Hour
- Weekday
- Weekend indicator
- Time period
- Weather groups
- City-State combinations

## Geographic Clustering

PySpark K-Means was used to group accident coordinates into broad geographic regions.

Multiple values of K were evaluated using the Silhouette Score.

The final run selected:

- **K = 10**
- **Silhouette Score = 0.7430**

The resulting clusters are interpreted as broad geographic groupings rather than accident hotspots.

## Dashboard

An interactive Dash dashboard was created to explore the processed dataset.

The dashboard includes:

- KPI summaries
- State and regional analysis
- Temporal patterns
- Weather analysis
- Road-feature comparisons
- Interactive maps
- Filtering by multiple attributes

A standalone HTML version of the dashboard was also created so the dashboard can be opened in a web browser without running the full Python notebook.

## Example Findings

Some descriptive findings from the final run include:

- California contained the highest number of reported accident records in the processed sample.
- Miami, Florida was the leading city by reported accident count.
- 7:00 AM had the highest reported accident frequency by hour.
- Clear/Fair was the most common weather group among reported accident records.

These findings describe patterns in the available dataset and should not be interpreted as direct measures of accident risk.

## Important Limitations

This project has several important limitations:

- Accident counts represent reported frequencies, not accident risk.
- Traffic volume and travel exposure are not available.
- Weather counts do not measure weather-related risk.
- Road-feature relationships are observational and do not prove causation.
- Severity represents traffic impact in the dataset and should not be interpreted directly as injury or fatality severity.
- K-Means clusters represent broad coordinate-based geographic regions, not true accident hotspots.
- Latitude and longitude are clustered using degree-based Euclidean distance rather than spherical or road-network distance.
- The 20% sample introduces some sampling variation.
- Reporting coverage varies across location and time.
- The 2023 data only covers January through March.

## Dataset

**US Accidents (2016–2023)**  
Author: Sobhan Moosavi  
Source: Kaggle  
DOI: 10.34740/KAGGLE/DS/199387  
License: CC BY-NC-SA 4.0

Dataset link:

https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents

## Project Files

- `BigData_test.ipynb` — complete analysis notebook
- `US_Accidents_Dashboard_Fixed.html` — standalone interactive dashboard

The original CSV dataset is not included in this repository because of its large file size. It can be downloaded from the Kaggle link above.

## What I Practiced

Through this project, I practiced:

- working with a multi-million-row dataset
- large-scale data preprocessing
- stratified sampling
- feature engineering
- data validation
- Polars-based analysis
- PySpark processing
- Spark MLlib K-Means clustering
- Silhouette Score model selection
- interactive Plotly visualizations
- Dash dashboard development
- communicating analytical findings with appropriate limitations

## Project Context

Originally developed as part of a university Big Data Analytics & Visualization course and later reviewed, corrected, and refined for portfolio use.
