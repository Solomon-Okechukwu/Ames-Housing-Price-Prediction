# Ames Housing Price Prediction

Machine Learning project predicting residential house sale prices using the Ames Housing dataset and comparing four regression models.

---

## 🔗 Project Resources

- [Download Raw Dataset](./AmesHousing.csv)
- [Download Cleaned Dataset](./AmesHousing_Cleaned.xls)
- [View Jupyter Notebook](./AmesHousing_ML.ipynb)

## Table of Contents

- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Dataset](#dataset)
- [Tools and Technologies](#tools-and-technologies)
- [Data Preparation](#data-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Feature and Target Separation](#feature-and-target-separation)
- [Data Preprocessing](#data-preprocessing)
- [Model Development](#model-development)
  - [Model 1: Linear Regression](#model-1-linear-regression)
  - [Model 2: Decision Tree Regressor](#model-2-decision-tree-regressor)
  - [Model 3: Random Forest Regressor](#model-3-random-forest-regressor)
  - [Model 4: Gradient Boosting Regressor](#model-4-gradient-boosting-regressor)
- [Model Evaluation](#model-evaluation)
- [Model Comparison](#model-comparison)
- [Results and Findings](#results-and-findings)
- [Conclusion](#conclusion)
- [Limitations](#limitations)
- [Project Notebook](#project-notebook)
- [References](#references)

---

## Project Overview

This project focuses on predicting residential house sale prices using machine learning techniques and the Ames Housing dataset.

The Ames Housing dataset contains detailed information about residential properties, including property size, quality, garage information, basement features, year built, neighborhood, and other housing characteristics.

The main objective of this project was to develop machine learning models that can learn the relationship between these property characteristics and the final sale price of a house.

The project follows a complete machine learning workflow, beginning with data inspection and exploratory data analysis, followed by data preparation, preprocessing, feature and target separation, model development, prediction, evaluation, and comparison.

Four regression algorithms were developed and evaluated:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor

The models were evaluated using Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and R² Score.

---

## Objectives

The main objectives of this project were to:

- Understand the structure and characteristics of the Ames Housing dataset.
- Explore the distribution of house sale prices.
- Identify important numerical and categorical variables.
- Investigate missing values and potential outliers.
- Prepare the dataset for machine learning.
- Separate predictor variables from the target variable.
- Handle numerical and categorical features appropriately.
- Build multiple regression models for house price prediction.
- Generate predictions on unseen test data.
- Evaluate model performance using standard regression metrics.
- Compare the performance of the four regression models.
- Identify the best-performing model for the dataset.

---

## Dataset

The dataset used in this project is the **Ames Housing dataset**, which contains information about residential properties in Ames, Iowa, and their corresponding sale prices.

The dataset contains:

- **2,930 observations**
- **82 columns**
- **43 categorical features**
- **39 numerical features**

The target variable is **SalePrice**, which represents the final selling price of each residential property.

The remaining relevant housing characteristics were used as predictor variables.

The dataset includes information about:

- Overall house quality
- Living area
- Basement area
- Garage characteristics
- Number of rooms
- Bathrooms
- Year built
- Year remodeled
- Lot size
- House type
- Neighborhood
- Other property characteristics

---

## Tools and Technologies

The following tools and Python libraries were used in this project:

- **Python** – programming language used for data analysis and machine learning.
- **Jupyter Notebook** – used for data exploration, preprocessing, modeling, and evaluation.
- **Pandas** – used for data manipulation and analysis.
- **NumPy** – used for numerical calculations.
- **Matplotlib** – used for data visualization.
- **Seaborn** – used for statistical data visualization.
- **Scikit-learn** – used for data preprocessing, machine learning models, and evaluation.
- **GitHub** – used for project documentation and portfolio presentation.

---

## Data Preparation

The Ames Housing dataset was inspected and prepared before developing the machine learning models.

The main preparation steps included:

- Loaded the Ames Housing dataset into a Pandas DataFrame.
- Examined the dataset structure using `shape`, `head()`, `info()`, and `describe()`.
- Checked for duplicate records.
- Identified missing values across the dataset.
- Examined the data types of the variables.
- Identified categorical and numerical features.
- Examined the distribution of the target variable, `SalePrice`.
- Investigated potential outliers using the Interquartile Range (IQR) method.
- Prepared the numerical and categorical variables for machine learning.
- Split the data into training and testing sets.

---

## Exploratory Data Analysis

Exploratory Data Analysis (EDA) was performed to understand the structure, distribution, and relationships within the Ames Housing dataset.

The analysis focused on:

- Examining the distribution of house sale prices.
- Identifying missing values.
- Understanding numerical and categorical variables.
- Investigating relationships between important housing characteristics and `SalePrice`.
- Examining correlations between numerical variables.
- Identifying potential outliers in house prices.
- Identifying variables with strong relationships with house prices.

The correlation analysis showed that variables such as **Overall Qual, Gr Liv Area, Garage Cars, Garage Area, Total Bsmt SF, 1st Flr SF, and Year Built** had relatively strong relationships with `SalePrice`.

---

## Feature and Target Separation

The objective of this project is to predict the selling price of a house.

Therefore, `SalePrice` was selected as the **target variable (y)**.

The remaining relevant housing characteristics were used as **input features (X)**.

Conceptually:

**X = House Features**

**y = SalePrice**

Unlike the Car Sales project, where a smaller number of selected columns were explicitly used as predictors, the Ames Housing dataset contains many numerical and categorical housing characteristics.

These features were therefore prepared through a preprocessing pipeline before being used by the machine learning models.

---

## Data Preprocessing

Because the Ames Housing dataset contains both numerical and categorical variables, preprocessing was required before training the machine learning models.

The preprocessing workflow included:

### Numerical Features

- Missing numerical values were handled using imputation.
- Numerical variables were prepared for model training.

### Categorical Features

- Missing categorical values were handled using imputation.
- Categorical variables were converted into numerical representations using **One-Hot Encoding**.

A `ColumnTransformer` and `Pipeline` from Scikit-learn were used to organize the preprocessing and modeling workflow.

This ensured that the same preprocessing steps were consistently applied to both the training and testing datasets and helped prevent data leakage.

---

## Model Development

Four regression algorithms were developed and evaluated for predicting house sale prices:

1. Linear Regression
2. Decision Tree Regressor
3. Random Forest Regressor
4. Gradient Boosting Regressor

---

## Model 1: Linear Regression

Linear Regression was used as the baseline model for the project.

### Results

- **MAE:** 17,849
- **RMSE:** 30,377
- **R²:** 0.885

The model provided a strong baseline for comparing the performance of more advanced regression algorithms.

---

## Model 2: Decision Tree Regressor

A Decision Tree Regressor was developed to capture non-linear relationships between housing characteristics and sale prices.

### Results

- **MAE:** 23,486
- **RMSE:** 34,933
- **R²:** 0.848

The Decision Tree performed worse than the Linear Regression model based on the evaluation metrics.

---

## Model 3: Random Forest Regressor

A Random Forest Regressor was developed by combining multiple decision trees to improve predictive performance and reduce the limitations of a single decision tree.

### Results

- **MAE:** 15,791
- **RMSE:** 26,686
- **R²:** 0.911

The Random Forest model performed better than both Linear Regression and the individual Decision Tree.

---

## Model 4: Gradient Boosting Regressor

A Gradient Boosting Regressor was used to build an ensemble model that sequentially improves predictions by focusing on errors made by previous trees.

### Results

- **MAE:** 15,140
- **RMSE:** 25,820
- **R²:** 0.917

Gradient Boosting produced the strongest performance among the four models tested.

---

## Model Evaluation

The models were evaluated using four standard regression metrics:

### Mean Absolute Error (MAE)

MAE measures the average absolute difference between predicted and actual house prices.

**Lower values indicate better performance.**

### Mean Squared Error (MSE)

MSE measures the average squared difference between predicted and actual values. Larger errors receive greater penalties.

**Lower values indicate better performance.**

### Root Mean Squared Error (RMSE)

RMSE is the square root of MSE and expresses prediction error in the same unit as the target variable.

**Lower values indicate better performance.**

### R² (R-Squared)

R² measures the proportion of variation in house prices explained by the model.

**Higher values indicate better performance.**

---

## Model Comparison

The performance of the four regression models was compared using MAE, RMSE, and R².

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Linear Regression | 17,849 | 30,377 | 0.885 |
| Decision Tree Regressor | 23,486 | 34,933 | 0.848 |
| Random Forest Regressor | 15,791 | 26,686 | 0.911 |
| Gradient Boosting Regressor | **15,140** | **25,820** | **0.917** |

### Best Model

**Gradient Boosting Regressor** achieved the best overall performance among the four models tested.

- Lowest MAE: **15,140**
- Lowest RMSE: **25,820**
- Highest R²: **0.917**

Therefore, Gradient Boosting was the best-performing model in this experiment.

---

## Results and Findings

The machine learning analysis produced the following key findings:

- Linear Regression provided a strong baseline with an R² of **0.885**.
- Decision Tree Regressor performed worse than the other models, with an R² of **0.848**.
- Random Forest improved substantially over the single Decision Tree, achieving an R² of **0.911**.
- Gradient Boosting achieved the strongest overall performance with an R² of **0.917**.
- Gradient Boosting also recorded the lowest MAE and RMSE.
- Ensemble tree-based methods performed particularly well for this house-price prediction problem.

---

## Conclusion

This project demonstrated a complete machine learning workflow for predicting residential house sale prices using the Ames Housing dataset.

The project covered:

- Data exploration
- Data preparation
- Exploratory Data Analysis
- Feature and target separation
- Data preprocessing
- Model development
- Prediction
- Model evaluation
- Model comparison

Four regression models were developed and compared.

Among the four models, **Gradient Boosting Regressor** achieved the best performance, with an **R² of 0.917**, **MAE of approximately $15,140**, and **RMSE of approximately $25,820** on the test dataset.

The results demonstrate that machine learning can effectively model the relationship between housing characteristics and residential sale prices.

---

## Limitations

Several limitations should be considered when interpreting the results:

- The dataset represents properties from a specific location and may not generalize to other housing markets.
- The dataset contains missing values that required preprocessing and imputation.
- Potential outliers may influence model performance.
- Model performance depends on the features available in the dataset.
- The models were evaluated using a single train-test split.
- Different train-test splits may produce slightly different results.
- Further hyperparameter tuning and cross-validation could potentially improve model performance.

---

## Project Notebook

The complete Python analysis, including data exploration, preprocessing, model development, prediction, and evaluation, is available in the Jupyter Notebook included in this repository.

The notebook provides the detailed implementation behind the results presented in this README.

---

## References

- Ames Housing dataset.
- Scikit-learn documentation.
- Pandas documentation.
- NumPy documentation.
- Matplotlib documentation.
- Seaborn documentation.
- Jupyter Notebook documentation.























