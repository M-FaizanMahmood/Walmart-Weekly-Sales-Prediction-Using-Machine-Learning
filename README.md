# Walmart Sales Data Exploration Report

## Introduction
This report presents an exploration of the Walmart sales dataset, aimed at analyzing sales trends, identifying key factors influencing sales performance, and developing predictive models. The dataset includes historical sales data from **45 Walmart stores** spanning from **February 5, 2010, to November 1, 2012**.

---

## 1. Libraries Utilized
The following Python libraries were utilized throughout the analysis:

- **NumPy (np):** For efficient numerical computations.
- **Pandas (pd):** For data manipulation and analysis using DataFrames.
- **Matplotlib (plt):** For static and interactive visualizations.
- **Seaborn (sns):** For statistical data visualization.
- **Warnings:** To suppress non-critical warnings.
- **Seaborn Theme/Style/Palette:** For cohesive visual styling.

---

## 2. Outlier Analysis

### 2.1 Weekly Sales Distribution
- **Mean Weekly Sales:** Approximately **$1 million**.
- **Upper Range:** Reaching up to **$2.7 million**.
- **Outliers:** **14 outliers** identified beyond the upper quartile limit, with values ranging from **$2.7 million to $3.7 million**.

### 2.2 Temperature Distribution
- **Mean Temperature:** Approximately **63°F**.
- **Outliers:** Recorded temperatures below **0°F**, indicating unusually cold weeks.

### 2.3 Unemployment Rate Distribution
- **Mean Unemployment Rate:** Approximately **7.8%**.
- **Upper Range:** Between **11% and 14.5%**.
- **Lower Range:** Values below typical limits, suggesting periods of unusually low unemployment.

---

## 3. Weekly Sales Analysis by Key Factors (Pair Plot)

### 3.1 Store Performance
- Stores with identifiers above **30** exhibit lower sales, generally remaining below **$2 million**.

### 3.2 Temperature Influence
- Sales volumes significantly decline when temperatures drop below **20°F**.

### 3.3 Fuel Prices Impact
- Increased fuel prices above **$4** correlate with decreased consumer spending, with weekly sales capped at **$2 to $2.3 million**.

### 3.4 Unemployment Rate Effect
- **Sales Performance:** Strong correlation between higher unemployment rates and lower weekly sales.
  - Sales maintain a range of **$2 million to $4 million** when unemployment is below **10%**.
  - Sales drop significantly, peaking only around **$2 million** when unemployment exceeds **10%**.

---

## 4. Weekly Sales / Unemployment Correlation
A direct relationship exists between rising unemployment rates and declining weekly sales. 

---

## 5. Data Preprocessing Steps

### 5.1 Handling Outliers
- **Weekly Sales:** Capped outliers at **$300,000**.
- **Temperature:** Applied the Interquartile Range (IQR) method for capping.

### 5.2 Date Column Formatting
- Converted the date column to **datetime** format using **%d-%m-%Y**.

### 5.3 Feature Extraction
- Extracted year, month, week, and quarter from the date column.

### 5.4 One-Hot Encoding
- Created new features from the **Holiday Flag** column through one-hot encoding.

### 5.5 Data Cleaning
- Dropped the original date and holiday flag columns for clarity.

---

## 6. Summary of Predictive Modeling

### 6.1 Library Usage Overview
- **LinearRegression (sklearn.linear_model):** For predicting continuous targets based on linear relationships.
- **DecisionTreeRegressor (sklearn.tree):** Captures non-linear relationships through feature value splits.
- **RandomForestRegressor (sklearn.ensemble):** Constructs an ensemble of decision trees for improved accuracy.
- **VotingRegressor (sklearn.ensemble):** Combines predictions from multiple models.
- **r2_score (sklearn.metrics):** Evaluates model performance via R-squared values.

### 6.2 Model Evaluation
- Trained and evaluated models using R² scores:
  - **Multiple Linear Regression:** R² Score = 0.1640
  - **Decision Tree Regressor:** R² Score = 0.9479
  - **Random Forest:** R² Score = 0.9633
  - **Voting Regressor:** R² Score = 0.8855
- **Random Forest Regressor** was chosen for its accuracy, achieving R² = **0.9949** post-training.
- Evaluation metrics:
  - **Mean Squared Error:** 11,565,053,725.15
  - **R-squared:** 0.9633

---

## 7. Dataset Overview

### 7.1 Dataset Description
- **Historical Sales Data:** From **45 Walmart stores**.
- **Time Frame:** **February 5, 2010 - November 1, 2012**.
- **Total Features:** **8 features** across **6,435 samples**.
- **Target Variable:** **Weekly_Sales**.

### 7.2 Feature Descriptions
- **Store (int):** Unique store identifier.
- **Date (object):** Sales week.
- **Weekly_Sales (float):** Sales amount for each store.
- **Holiday_Flag (int):** Indicates if the week included a holiday.
- **Temperature (float):** Temperature on the day of sale.
- **Fuel_Price (float):** Regional fuel cost.
- **CPI (float):** Consumer Price Index.
- **Unemployment (float):** Unemployment rate.

### 7.3 Data Quality
- **No Missing Values:** All columns are complete.
- **Unique Values:** 
  - Store: 45
  - Date: 143 unique weeks
  - Weekly_Sales: 6,435 records
  - Holiday_Flag: 2 values (1 and 0)
  - Temperature: 3,528 readings
  - Fuel_Price: 892 variations
  - CPI: 2,145 values
  - Unemployment: 349 rates

---

## Conclusion
The analysis reveals critical insights into the factors influencing Walmart sales, including seasonal variations and economic indicators. The predictive modeling indicates a high correlation between sales and unemployment rates, with models such as the Random Forest Regressor proving effective for sales predictions. This report underscores the importance of continuous analysis to adapt to changing consumer behaviors and economic conditions.
