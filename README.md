# InsurancePremiumPrediction-Regression-Analysis
A linear regression model to predict health insurance charges based on customer demographics, achieving 76% accuracy through statistical feature optimization.

## 📊 Project Overview
A machine learning project that predicts health insurance charges based on customer demographics and health factors. This project demonstrates the complete data science workflow from exploratory data analysis through model refinement, achieving a robust predictive model that explains 78% of variance in insurance premiums.
The model helps insurance companies:
- Accurately predict insurance premiums based on customer profiles.
- Identify key factors driving insurance costs.
- Optimize pricing strategies with data-driven insight.

## 🎯 Results Summary
### Initial Model Performance
- Features Used: 8
  -   age
  -   BMI
  -   children
  -   sex_male
  -   smoker_yes
  -   region_northwest
  -   region_southeast
  -   region_southwest
  
- R² Score: 0.760
- RMSE: $5,942.82
- Key Insight: Model included statistically insignificant features (sex_male, region_northwest, region_southwest)

### Refined Model Performance
- Features Used: 5 
  - age
  - BMI
  - children
  - smoker_yes
  - region_southeast
- R² Score: 0.761
- RMSE: $5,938.98
- Improvement: Maintained predictive accuracy while reducing model complexity by 37.5%
  
## 🔍 Methodology
### 1.Data Preprocessing
- Removed duplicate records from 1,338 total entries.
- Applied one-hot encoding to categorical variables (sex, smoker, region).
- Implemented MinMax scaling (0-1 range) for numerical features.
- Handled multicollinearity by dropping redundant encoded columns.

### 2.Feature Engineering
- Converted categorical variables to binary indicators.
- Normalized continuous variables for improved model convergence.
- Removed dummy variable trap by dropping one category per feature.

### 3.Model Development
- Split data: 80% training, 20% testing (random_state=25).
- Implemented Ordinary Least Squares (OLS) regression.
- Conducted statistical significance testing (p-value < 0.05).
- Performed model refinement by removing insignificant predictors.

### 4.Statistical Analysis
- Comprehensive OLS regression analysis using statsmodels.
- Feature significance testing with p-values.
- Model diagnostics (Durbin-Watson, Jarque-Bera tests).
  
## 📈 Visualizations
### Correlation Heatmap: Shows relationships between numeric features
- Strong positive correlation between age and charges.
- Moderate correlation between BMI and charges.

### Outlier Analysis: Box plots identifying outliers in features
- BMI showed 9 outliers (0.67% of data).
- Decision made to retain outliers as they represent valid extreme cases.

### Feature Importance: Statistical significance of predictors
- Smoking status: p < 0.001 (highly significant).
- Age and BMI: p < 0.001 (highly significant).
- Sex: p = 0.913 (not significant).
  
## 🔑 Key Findings
### 1.Smoking is the Dominant Factor
- Smokers pay approximately $23,040 more in premiums.
- Single most impactful predictor in the model.

### Age and BMI are Secondary Drivers
- Each standardized unit increase in age adds $11,680 to premiums.
- Each standardized unit increase in BMI adds $12,230 to premiums.

### Gender Has No Significant Impact
- Statistical analysis shows gender doesn't affect premium pricing.
- Suggests equitable pricing across sexes.

### Regional Differences are Minimal
- Only Southeast region shows slight significance (-$936).
- Most regional variations are not statistically significant.

### Model Parsimony Achieved
- Reduced features from 8 to 5 without performance loss.
- Improved model interpretability and reduced overfitting risk.

## 📁 Dataset Information
**Size: 1,338 records**
**Features:**
- Numerical:
  - Age (18-64 years)
  - BMI (Body Mass Index)
  - Children (0-5)
  - Charges (Target variable: $1,121 - $63,770)

- Categorical:
  - Sex (Male/Female)
  - Smoker (Yes/No)
  - Region (Northeast, Northwest, Southeast, Southwest)
 🛠️ Technologies Used

## 🛠️ Module Usage
Python 3.x
Libraries:
- pandas, numpy (Data manipulation)
- scikit-learn (Machine learning)
- statsmodels (Statistical analysis)
- matplotlib, seaborn (Visualization)
