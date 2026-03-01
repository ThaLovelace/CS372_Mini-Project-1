# CS372_Mini-Project-1
# Sleep Disorder Screening System using Machine Learning

## Project Overview
This repository contains the source code and documentation for a machine learning project aimed at predicting sleep disorders based on lifestyle and health metrics. The goal of this project is to develop a pre-screening system to help identify individuals at risk of Insomnia or Sleep Apnea, thereby reducing the burden on medical facilities and providing an accessible early-warning tool.

## Dataset
The project utilizes the **Sleep Health and Lifestyle Dataset**, which consists of 374 records and 13 features. 
* **Target Variable:** `Sleep Disorder` (Classes: None, Insomnia, Sleep Apnea)
* **Key Features:** Sleep Duration, Quality of Sleep, Physical Activity Level, Stress Level, BMI Category, Blood Pressure, Heart Rate, and Daily Steps.

## Repository Structure
The project workflow is divided into structured Jupyter Notebooks to ensure readability and maintainability:

* `preprocessing.ipynb`: Handles data cleaning, missing values imputation, categorical encoding, and feature scaling. Outputs the `cleaned_data.csv`.
* `feature_importance.ipynb` / `feature_selection.ipynb`: Analyzes feature importance using Tree-based methods and Permutation Importance to select the most relevant features for modeling.
* `modeling.ipynb`: The core modeling file. It covers:
  * Splitting data into Training (80%) and Testing (20%) sets using Stratified Sampling.
  * Hyperparameter tuning using **GridSearchCV** with **5-Fold Cross-Validation**.
  * Training and evaluating 4 machine learning models: **k-Nearest Neighbors (kNN), Decision Tree, XGBoost, and Neural Network (MLP)**.
  * Model evaluation using Accuracy, Precision, Recall, and F1-score.

## Methodology & Model Selection
All models were rigorously evaluated to prevent overfitting and underfitting by comparing Cross-Validation (CV) scores with Test Evaluation scores. 

**Results Summary:**
* **Decision Tree:** Test Accuracy **97.33%** (Best)
* **Neural Network (MLP):** Test Accuracy 96.00%
* **k-Nearest Neighbors (kNN):** Test Accuracy 94.67%
* **XGBoost:** Test Accuracy 93.33%

**Conclusion:** The **Decision Tree** model was selected as the final model. Not only did it achieve the highest test accuracy (97.33%) and a perfect F1-score (1.00) for the 'None' class, but it is also a transparent, interpretable model (White-box). This interpretability allows medical professionals to explain the risk factors (If-Else rules) clearly to patients, making it highly suitable for healthcare applications.

## How to Run the Code
The code is designed to run seamlessly. The datasets are loaded directly via raw GitHub URLs, ensuring no local path dependencies.

1. Clone the repository:
   ```bash
   git clone https://github.com/ThaLovelace/CS372_Mini-Project-1.git
```

2. Install the required dependencies:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn xgboost

```


3. Run the Jupyter Notebooks in the following order:
* `preprocessing.ipynb`
* `feature_selection.ipynb`
* `modeling.ipynb`
