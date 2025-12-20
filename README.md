#  Russian Alcohol Consumption Analysis: A KNN Approach

## **Project Overview**
This repository contains a comprehensive Machine Learning analysis of alcohol consumption across different Russian regions. The project leverages **K-Nearest Neighbors (KNN)** to perform two distinct tasks:
1.  **Classification:** Categorizing regions into "High", "Medium", or "Low" consumption levels.
2.  **Regression:** Predicting the actual volume of consumption based on historical trends and regional features.

---

## ** The Data**
The dataset tracks regional consumption from 1998 to 2016 across several categories:
* **Categories:** Wine, Beer, Vodka, Champagne, and Brandy.
* **Preprocessing:** Handled missing values (approx. 60 per category) using mean imputation and conducted regional grouping to identify temporal trends.

---

## ** Machine Learning Pipelines**

### **1. KNN Classification (Consumption Levels)**
* **Objective:** Predict whether a region falls into a High, Medium, or Low consumption tier.
* **Optimization:** Performed a **GridSearchCV** to find the best hyperparameters.
* **Best Parameters:** `{'metric': 'euclidean', 'n_neighbors': 7, 'weights': 'distance'}`
* **Performance:**
    * **Accuracy:** 95%
    * **Precision (High):** 0.99
    * **F1-Score:** 0.95 (Avg)

### **2. KNN Regression (Volume Prediction)**
* **Objective:** Forecast the actual numeric consumption values.
* **Best Parameters:** `{'metric': 'manhattan', 'n_neighbors': 2, 'weights': 'distance'}`
* **Performance:**
    * **R-squared ($R^2$):** 0.7761
    * **Mean Absolute Error (MAE):** 8.44

---

## **🔍 Key Insights from EDA**
* **High Volatility:** Certain regions show significant spikes in specific spirits (Vodka vs. Wine) depending on the year.
* **Model Fit:** The "Manhattan" distance metric outperformed "Euclidean" for the regression task, suggesting that the features have independent, additive effects on the consumption volume.
* **Actual vs. Predicted:** The model successfully captured the downward trend in specific spirits over the last decade while maintaining low error margins.

---

## ** Tech Stack**
* **Analysis:** `Pandas`, `NumPy`
* **Machine Learning:** `Scikit-Learn` (GridSearchCV, KNeighborsRegressor, KNeighborsClassifier)
* **Visualization:** `Matplotlib`, `Seaborn`


[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/JustineDataEng/Alcohol-Consumption-Analysis-KNN/blob/main/ML_KNN_Project.ipynb)
