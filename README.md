# Supervised Machine Learning: Regression Project for House Price Prediction

This repository contains the capstone project for the IBM "Supervised Machine Learning: Regression" course. The project focuses on developing, training, and evaluating various regression models to predict house prices based on a given dataset.

---

### Project Overview

The primary objective was to build and compare the performance of several regression models, including **Linear Regression**, **Polynomial Regression**, **Ridge**, and **Lasso**. The process involved a systematic workflow from data preparation and model training to hyperparameter tuning and a final evaluation to identify the most accurate model for the task.

---

### Methodology

The project followed these key steps:

* **Data Preparation**: The project began by loading the `house_price_regression_dataset.csv`. A thorough cleaning process was performed, which revealed the dataset was exceptionally clean, containing **no missing values, duplicates, or outliers**. As a result, extensive feature engineering was deemed unnecessary.

* **Data Splitting**: The dataset was split into a 70% training set and a 30% testing set. A `random_state` was set to ensure the reproducibility of the results.

* **Model Training and Hyperparameter Tuning**: Several models were trained using `scikit-learn`'s `Pipeline` to streamline the workflow.
    * **Polynomial Regression**: `GridSearchCV` was used to find the optimal polynomial degree, which was determined to be 1 (effectively a Linear Regression model).
    * **Ridge Regression**: `RidgeCV` was employed to automatically find the best regularization strength (`alpha`) through 5-fold cross-validation.
    * **Lasso Regression**: `LassoCV` was used similarly to identify the optimal `alpha` for the Lasso model, also with 5-fold cross-validation.

* **Evaluation**: The performance of all models was measured using the **Root Mean Squared Error (RMSE)** metric, where a lower score indicates a better fit.

---

### Results

The evaluation yielded the following RMSE scores for each model:

| Model | RMSE |
| :--- | :--- |
| **Linear (Polynomial Degree 1)** | 10113.409759 |
| **Lasso** | 10113.409759 |
| **Ridge** | 10119.213835 |

* The **Linear** and **Lasso** regression models performed the best, with nearly identical scores.
* The **Ridge** model was slightly less accurate but still highly competitive.
* Visualizations, including plots of predicted vs. actual values, confirmed that all models tracked the true house prices very closely.

---

### Conclusion

For this specific dataset, the simpler **Linear Regression** model and the **Lasso Regression** model proved to be the most effective predictors of house prices. he strong performance across all models suggests the underlying relationships in the data are predominantly linear.

However, it is important to consider the project's main limitation: the dataset's small size of 1000 samples and 7 features. This may constrain the models' ability to generalize to new, unseen data.

---

### Next Steps

The project report suggests several avenues for future work to enhance model performance and robustness:
* Expand the dataset with more samples and relevant features.
* Conduct more advanced feature engineering.
* Explore more complex ensemble models (e.g., Random Forest, XGBoost).
* Implement more rigorous cross-validation techniques, such as repeated K-fold cross-validation, to get more stable performance estimates.
