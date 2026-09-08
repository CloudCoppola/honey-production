# Honey Production - Linear Regression Analysis

A machine learning project analysing historical honey production in the United States and using linear regression to investigate changes in total honey production over time.

## Overview

Honeybees play an important role in agriculture and food production through both honey production and pollination. Changes in honeybee populations and honey production have therefore attracted ecological and agricultural interest.

This project examines historical U.S. honey production data from 1998 to 2012 to investigate how total honey production changes over this period.

A linear regression model quantifies the relationship between year and total production and explores how to extrapolate the historical trend to future years.

The project provides a practical introduction to data preparation, exploratory visualisation, linear regression, prediction, and model interpretation.

## Objectives

The project aims to:

- Explore historical honey production data across U.S. states 
- Aggregate state-level production data to examine annual production trends
- Visualise the relationship between year and total honey production
- Fit a linear regression model to the historical data 
- Interpret the fitted regression relationship
- Use the model to explore future production estimates based on the historical

## Dataset

The project used the **Honey Production in the USA (1998-2012)** dataset available on Kaggle. The data originates from the **National Agricultural Statistics Service (NASS)** of the U.S. Department of Agriculture (USDA).

The dataset contains annual honey production statistics reported by U.S. states between 1998 and 2012. The cleaned `honeyproduction.csv` dataset variables are provided below:

| Variable      | Description                        | Unit       |
|---------------|------------------------------------|------------|
| `state`       | U.S. state                         | —          |
| `numcol`      | Number of honey-producing colonies | Colonies   |
| `yieldpercol` | Honey yield per colony             | Pounds     |
| `totalprod`   | Total honey production             | Pounds     |
| `stocks`      | Honey stocks held by producers     | Pounds     |
| `priceperlb`  | Average price per pound            | US dollars |
| `prodvalue`   | Value of honey production          | US dollars |
| `year`        | Reporting year                     | Year       |

Some states are excluded from particular years where reporting the data could disclose information about individual operations. Additionally, reported values are subject to rounding, meaning calculated total may not always exactly reproduce the published figures. 

**Dataset:** [Honey Production in the USA (1998–2012) - Kaggle](https://www.kaggle.com/datasets/jessicali9530/honey-production/data)

**Original data source:** National Agricultural Statistics Service (NASS), U.S. Department of Agriculture

## Methodology

The analysis follows a simple machine learning workflow.

### 1. Data Acquisition

The dataset is retrieved programmatically from Kaggle using `kagglehub`. The avoids storing a duplicate copy of the dataset in the repository and makes data acquisition reproducible.

### 2. Data Exploration and Preparation 

The dataset is inspected using pandas before grouping the relevant production data by year. State-level production values are aggregated to obtain total annual honey production for the available period. 

### 3. Exploratory Visualisation 

Annual honey production is plotted against year to examine the historical relationship and identify the overall production trend.

### 4. Linear Regression

A linear regression model is fitted using scikit-learn, with: 

- **Feature (X)** - year
- **Target (y)** - total annual honey production

The fitted regression line provides a simple representation of the historical relationship between time and production. 

### 5. Prediction

The fitted model extrapolates the observed historical trend to future years. 

Interpret these predictions as an extension of the historical linear trend, not as a forecast incorporating ecological, economic, climatic, or agricultural factors.

### Results

The linear regression analysis identified a negative relationship between year and honey production over the historical period represented in the dataset. The fitted regression line therefore indicates that honey production tended to decrease as year increased.

When the fitted linear trend was extrapolated to 2050, the model estimated honey production of approximately 186,545 lbs.

This value should not be interpreted as a reliable forecast of honey production in 2050. The model uses year as its only explanatory variable and assumes that the historical linear relationship continues beyond the observed 1998–2012 data.

## Technologies

The project uses: 

- **Python** - analysis and modelling 
- **pandas** - data manipulation and aggregation 
- **NumPy** - numerical operations
- **Matplotlib** - data visualisation
- **scikit-learn** - linear regression
- **KaggleHub** - programmatic dataset retrieval 
- **Jupyter** - interactive notebook workflow

## Installation 

Clone the repository:

``` 
git clone <repository-url>
cd <repository-name>
```

Create and activate Python environment, then install the project dependencies:

```
pip install -r requirements.txt
```

The notebook can then be opened and run using a suitable Python kernel.

## What This Project Demonstrates

This project demonstrates practical experience with:

- Acquiring an external dataset programmatically
- Exploring and manipulating tabular data with pandas
- Aggregating data for analysis
- Visualising relationships using Matplotlib
- Preparing features and targets for machine learning
- Implementing linear regression with scikit-learn
- Generating predictions from a fitted regression model
- Interpreting a simple machine learning model
- Structuring a reproducible Python data analysis project

## Limitations

The linear regression model considers year as the sole explanatory variable. It therefore captures a historical temporal trend rather than the underlying causes of changes in honey production. 

The model does not account for factors such as colony number, yield per colony, weather, disease, pesticide exposure, agricultural practices, market conditions, and other environment or economic variables.

Furthermore, extrapolating a linear relationship beyond the 1998-2012 observation period assumes that the historical trend continues. Future estimates should therefore be treated as illustrative model predications rather than reliable forecasts of future U.S. honey production.

## Project Background 

This project was initially completed as part of the **Codecademy Machine Learning and AI Engineering** learning pathway. It has subsequently been organised as a standalone portfolio project to document and demonstrate the machine learning concepts and Python techniques applied during the lab exercise.

## Acknowledgements 

The **National Agricultural Statistics (NASS)** of the **U.S. Department of Agriculture (USDA)** originally published the honey production data, and it is distributed in cleaned form through the Kaggle dataset used in this project. 

The original Codecademy lab exercise provided the basis for the analysis undertaken in this project. 