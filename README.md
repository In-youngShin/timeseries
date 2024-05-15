# Predicting Country-Level Suicide Rates

## Introduction
This project aims to predict country-level suicide rates using time-series data based on machine learning algorithims. 

## Dataset
The dataset used in this project is sourced from Kaggle and includes socio-economic information alongside suicide numbers and rates by year and country from 1990 to 2022. The data was obtained from the United Nations association and the World Bank. Additionally, information about the major religion of each country was gathered from Wikipedia and merged with the dataset.

### General Information on Dataset
- 117 countries from five different continents are included in the dataset.
- Years reported: 1990 to 2022
- **Target Variable (y):** Suicide rate per 100k population
- **Input Features (x):**
  - Region: Continent each country belongs to
  - Country: Name of the country
  - GDP: Total economic output in US Dollars
  - GDP Per Capita: Economic output per person measured in US dollars
  - Population: Total population of the country
  - Inflation Rate: Annual increase in consumer prices
  - Employment Ratio: Percentage of population aged 15+ that is employed
  - Religion: Majority religion adhered to in the country

## Data Engineering 
### Creating Lag Feature 
Handling time-series data often involves creating lag features, representing shifts of data one or more steps backward in time. Two common methods for handling lag features are:
1. **Lagged Models:** This method uses observations from previous time steps as lag features.
2. **Difference-Based Models:** This approach employs the differences between the current time and previous times.

In this project, both approaches were applied. Lag features were created using Python Pandas shift. For the difference-based approach, the differenced data were calculated by subtracting each observation from its respective observation at the previous time step for both the target variable and the lagged features.


## Modeling 
### Base Models
Before moving to time-series modeling, regression analysis was performed on the data without lag features. Polynomial regressions ranging from degree 1 to 5 were applied to these models, utilizing the sklearn package.

### Polynominal Regressions on Time-series Data
Once lag features were engineered into the dataset, various machine learning algorithms became applicable. In this project, polynomial regression from degree 1 to 5 was employed alongside other algorithms. Three datasets were prepared with 3, 4, and 5 lag features respectively. These regression models were implemented using the sklearn package.

### Ridge Regression with Polynomial Models
Considering the potential for overfitting in time-series datasets with lag features, regularization techniques may be necessary. If overfitting is observed in the polynomial models, ridge regression will be conducted. These regression models were implemented using the sklearn package.

