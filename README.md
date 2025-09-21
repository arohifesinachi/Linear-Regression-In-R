# Linear Regression Analysis of Medical Expenses

This repository demonstrates how to build, evaluate, and validate a **multiple linear regression model** in R using the classic **health insurance expenses dataset**. The project walks through the full workflow — from data exploration to assumption testing and model validation — to show how regression can be applied to real-world medical cost prediction.

##  Dataset Description

The dataset (`expenses.csv`) contains information on **1,338 health insurance beneficiaries** with the following variables:

- **age**: Age of the primary beneficiary (18–64 years).  
- **sex**: Gender of the insurance contractor (female, male).  
- **bmi**: Body Mass Index (BMI), a measure of body fat (kg/m²).  
- **children**: Number of children/dependents covered by insurance.  
- **smoker**: Smoking status (yes/no).  
- **region**: Residential area in the US (northeast, southeast, southwest, northwest).  
- **charges**: Individual medical costs billed by health insurance.  

This dataset is widely used for regression modeling because it includes both numerical and categorical predictors, with a positively skewed target variable (`charges`).

---

##  Objective

The main objective is to **predict medical costs (`charges`)** using demographic and lifestyle factors. The analysis highlights:  

- How to preprocess and explore the dataset.  
- How to build and interpret a multiple linear regression model.  
- How to test assumptions (normality, multicollinearity, homoscedasticity, autocorrelation).  
- How to validate model performance with metrics such as R², RMSE, AIC/BIC.  

---

##  Workflow

1. **Data Preprocessing**
   - Load dataset, check structure, handle categorical variables.  
   - Summarize descriptive statistics and check for missing values/outliers.  

2. **Exploratory Data Analysis (EDA)**
   - Visualize distributions with histograms and boxplots.  
   - Explore correlations using a correlation matrix and corrgrams.  
   - Detect outliers and skewness in `charges`.  

3. **Model Building**
   - Fit a multiple linear regression model using `lm()`.  
   - Train-test split (70/30) with the `caret` package.  
   - Regression equation:  
     ```
     charges ~ age + sex + bmi + children + smoker + region
     ```

4. **Model Interpretation & Validation**
   - Interpret coefficients, p-values, and significance levels.  
   - Check R² and Adjusted R² for model fit.  
   - Validate using:  
     - F-test (overall significance)  
     - AIC/BIC (model comparison)  
     - RMSE (prediction accuracy)  
   - Test assumptions:
     - Residual plots & Q-Q plots (normality).  
     - Scale-Location plot (homoscedasticity).  
     - VIF test (multicollinearity).  
     - Durbin-Watson test (autocorrelation).  

5. **Prediction on Test Data**
   - Use the trained model to predict charges on unseen data.  
   - Calculate R² on test set for generalization performance.  

---

##  Key Findings

- **Charges are positively skewed**, with a few extremely high values.  
- **Strong predictors**: age, BMI, and smoker status significantly affect charges.  
- **Model Fit**: R² ≈ 0.75 on training data and ≈ 0.72 on test data — indicating a fairly strong model.  
- **Limitations**: Some assumptions (e.g., homoscedasticity) are not fully met, suggesting possible improvements via transformations or alternative models (e.g., log-transformation of charges).  

---

## Conclusion

This project demonstrates the end-to-end application of linear regression in R. It highlights not just how to fit a model, but also why validating assumptions and metrics is essential before deploying the model.

The methods here can be adapted to other regression problems where continuous outcomes need to be predicted.


---

## Author
Ifesinachi Aroh
Data Scientist
Auburn University
