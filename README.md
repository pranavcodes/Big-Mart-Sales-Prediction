### Project Title
Big Mart Sales Prediction: A Data-Driven Approach

### Approach Overview
This project's goal is to predict retail sales for Big Mart and identify key factors influencing them. The model's performance is evaluated using the **Root Mean Squared Error (RMSE)** metric.

* **Data Preparation:** The process began with extensive data cleaning. I handled missing values in `Item_Weight` and `Outlet_Size`, standardized inconsistent categories in `Item_Fat_Content`, and imputed unrealistic zero values in `Item_Visibility`.
* **Feature Engineering:** I created new, more informative features to enhance the model's predictive power. This included deriving `Outlet_Age` from the establishment year and creating high-level `Item_Category` features from the `Item_Identifier`.
* **EDA Insights:** Exploratory Data Analysis revealed key relationships. I found that `Item_MRP` has a strong positive correlation with sales, while `Outlet_Type` is a highly influential categorical feature. A logarithmic transformation was applied to the skewed target variable, `Item_Outlet_Sales`, to improve model performance and prevent negative predictions.
* **Modeling:** The final solution uses an end-to-end machine learning pipeline. After establishing a baseline with a simple model, I used **XGBoost** and fine-tuned its hyperparameters using **Optuna Bayesian optimization** to arrive at the most accurate model possible.

### Key Findings
* **`Item_MRP`** is the single most important predictor of sales.
* **`Outlet_Type`** (specifically `Supermarket Type3`) is a critical factor influencing a store's sales performance.
* The model discovered that **`Outlet_Age`** and **`Item_Visibility`** have significant predictive power, even though their linear correlation with sales was weak.

### Repository Contents
* `notebook/`: Contains the main Jupyter Notebook (`Big_Mart_EDA_Notebook.ipynb`) with all the code, analysis, and visualizations.
* `scripts/`: Holds any standalone Python scripts for model training or utility functions.
* `data/`: Includes the raw data files (`train.csv`, `test.csv`, and `sample_submission.csv`).
* `submission/`: The final `submission.csv` file with the model's predictions.
* `README.md`: This file, providing a high-level overview of the project and methodology.
