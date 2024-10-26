# Walmart-Weekly-Sales-Prediction-Using-Machine-Learning
This project uses advanced predictive modeling to forecast weekly sales with 99.49% accuracy, leveraging factors like store attributes, temperature, and holidays to drive data-driven decision-making for revenue growth.

### Project Outcomes & Conclusion

**Summary:**

This project aimed to predict weekly sales based on various influencing factors, including store attributes, temperature, fuel prices, CPI, unemployment rates, and holiday effects. The structured approach encompassed the following steps:

1. **Data Exploration:**
   - Imported essential libraries and the dataset.
   - Examined data types, identified null values, and checked unique values in categorical features.
   - Conducted statistical summaries, revealing a maximum weekly sales figure of 3,818,686.45, with typical weekly sales capped at 300,000 due to outlier management.

2. **Exploratory Data Analysis (EDA):**
   - Analyzed the target variable's distribution, showing a right skew.
   - Utilized counter plots for categorical variables and box plots for numerical features, highlighting outliers.
   - Created pair plots to understand feature relationships, noting multicollinearity and potential outliers.

3. **Data Pre-processing:**
   - Removed duplicates and imputed null values.
   - Applied one-hot encoding to categorical variables and capped outliers using the IQR method.
   - Updated dataset size, reflecting rows dropped during preprocessing.

4. **Data Manipulation:**
   - Split the data into training and testing sets.
   - Standardized features to ensure equal contribution to model training.

5. **Feature Selection/Extraction:**
   - Analyzed correlations among features, retaining those most relevant for model training.

6. **Predictive Modeling:**
   - Implemented Multiple Linear Regression, Decision Tree Regressor, Random Forest, and Ensemble Techniques.
   - Evaluated model performance using R² scores, with Random Forest achieving the highest accuracy at 0.9949.

A user-friendly interface allowed stakeholders to input real-time data for weekly sales predictions based on parameters like store number, temperature, and holiday flags.

In conclusion, the project effectively analyzed the factors affecting weekly sales and developed a robust predictive model. The high accuracy of the Random Forest Regressor illustrates its applicability in real-world sales forecasting, enabling data-driven strategic planning.
