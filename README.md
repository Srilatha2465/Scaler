# Scaler
**Insurance Cost Prediction:**

**Problem Statement:**

Insurance companies often rely on generalized actuarial tables to determine premiums, which fail to capture individual-level risk variations. This can lead to inaccurate pricing—either underpricing high-risk individuals or overcharging low-risk customers.

The goal of this project is to build a data-driven machine learning model that predicts individual insurance costs based on demographic and health-related attributes, enabling personalized, fair, and competitive premium pricing.

**Target Metric:**

To evaluate model performance, the following metrics were used:

- RMSE (Root Mean Squared Error) → Measures prediction error magnitude
- MAE (Mean Absolute Error) → Measures average absolute deviation
- R² Score → Indicates model explanatory power

Primary focus: Minimizing RMSE while maintaining high R²

**Approach & Methodology:**

**1) Exploratory Data Analysis (EDA):**
   
- Analyzed distributions of key variables like age, BMI, and premium costs
- Identified right-skewness in insurance charges → applied log transformation
- Detected outliers using IQR method
- Explored relationships:
    - Strong correlation between BMI, age → premium
    - Moderate impact of surgeries and chronic conditions

**2) Hypothesis Testing:**

Statistical tests were used to validate assumptions:

- T-Test (Chronic Disease Impact)
→ Chronic conditions significantly increase costs
- ANOVA (Number of Surgeries)
→ Premium varies significantly across surgery groups
- Chi-Square Test
→ Association between health conditions and family history

These tests confirmed that observed patterns are statistically significant.

**3) Feature Engineering:**
   
- Created age groups and BMI categories
- Built risk_score combining diseases, and surgeries
- Added interaction features (age × BMI)
- Applied log transformation on target variable
- Encoded categorical variables and scaled features

**4) Model Building:**
   
- Baseline Model:
    - Linear Regression → Established baseline performance
- Advanced Models:
    - Decision Tree
    - Random Forest
    - Gradient Boosting
    - Neural Network (MLP)

Tree-based models performed better due to their ability to capture non-linear relationships.

**5) Model Evaluation & Validation:**
   
- Used train-test split (80-20)
- Applied 5-fold cross-validation to ensure robustness
- Compared models using RMSE, MAE, and R²

**Best Model:** Random Forest / Gradient Boosting

- Lowest RMSE
- Highest R²
- Better generalization across folds

**Key Insights:**

- BMI (obesity) significantly increases premiums
- Age has a steady positive relationship with cost
- Chronic diseases and surgeries elevate risk substantially
- Combined risk factors create exponentially higher premiums

**Business Recommendations:**

- Implement risk-based personalized pricing instead of flat premiums
- Introduce wellness programs (fitness incentives)
- Design targeted insurance plans for high-risk groups
- Encourage early enrollment to lock lower premiums
- Use model insights for customer segmentation and marketing strategies

**Conclusion:**

This project demonstrates how machine learning can transform traditional insurance pricing into a data-driven, personalized system, improving both profitability for insurers and fairness for customers.
