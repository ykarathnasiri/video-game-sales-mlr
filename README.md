# Video Game Sales — Multiple Linear Regression

This repository contains a Jupyter Notebook that analyzes the Video Game Sales dataset and applies Multiple Linear Regression (MLR) to predict **Global Sales**.  
The project demonstrates a full end-to-end regression workflow, from data preprocessing and exploratory data analysis (EDA) to model fitting, validation of statistical assumptions, and saving the final model for future use.

---

## Project Overview

The objective of this project is to build and evaluate a regression model that predicts global video game sales based on attributes such as platform, publisher, genre, region-specific sales, and year of release.  

The notebook:
- Cleans and preprocesses the dataset  
- Encodes categorical features using label encoding and mean encoding  
- Applies log transformation to address skewness in sales data  
- Fits multiple OLS regression models  
- Validates key regression assumptions:
  - Linearity
  - Normality of residuals
  - Homoscedasticity
  - Independence of errors
  - Multicollinearity  
- Selects and saves the final model for predictions  
- Provides a sample prediction workflow  

---

## Repository Structure

```
video-game-sales-mlr/
│── video_game_sales_multiple_linear_regression.ipynb   # Main notebook with full workflow
│── data/
│    └── video_games_sales.csv                         # Dataset (if distributable)
│── models/
│    └── best_global_sales_model.joblib                # Saved regression model
│── README.md                                          # Project documentation
```

---

## Installation and Requirements

Clone the repository and install the required dependencies:

```bash
git clone https://github.com/<your-username>/video-game-sales-mlr.git
cd video-game-sales-mlr
pip install -r requirements.txt
```

Alternatively, install dependencies manually:

```bash
pip install pandas numpy matplotlib seaborn statsmodels scikit-learn scipy joblib
```

---

## Usage

1. Open the Jupyter Notebook:
   ```bash
   jupyter notebook video_game_sales_multiple_linear_regression.ipynb
   ```
2. Run all cells sequentially to reproduce the analysis.  
3. Use the sample input section at the end of the notebook to test predictions with new data.  
4. The trained model is saved as `best_global_sales_model.joblib` and can be reused for predictions in other applications.

---

## Results Summary

- **Final Model:** OLS regression on `Log_Global_Sales`.  
- **Key Predictors:** `Genre_encoded`, `year`, `Publisher_encoded`, `Platform_encoded`, `Log_NA_Sales`.  
- **Diagnostics:**  
  - Residuals vs Fitted plot: no strong violations of linearity  
  - Q–Q plot and Shapiro–Wilk test: residuals not perfectly normal but acceptable  
  - Durbin–Watson ≈ 2: no evidence of autocorrelation  
  - VIF values within acceptable range after removing highly correlated predictors  

The model is effective for prediction, but caution is advised when making strict statistical inferences.

---

## Notes

- Categorical encodings for `Publisher` and `Platform` must match those derived during training when predicting on new data.  
- If the dataset is updated or extended, encodings and transformations must be recomputed.  
- The workflow can be extended to include Ridge, Lasso, or other regression approaches for comparison.

---
