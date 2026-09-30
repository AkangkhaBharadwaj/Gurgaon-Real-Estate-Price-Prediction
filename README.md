# Gurgaon Real Estate Price Prediction Using Machine Learning

## 📌 Project Overview

This project develops a machine learning-based system for predicting residential property prices in Gurgaon (Gurugram) using real estate data.

The project covers the complete machine learning workflow, including data collection, data cleaning, exploratory data analysis (EDA), feature selection, preprocessing, model training, model evaluation, price prediction, and feature importance analysis.

---

## 🎯 Objectives

* Clean and preprocess Gurgaon real estate data
* Perform exploratory data analysis to understand property-price patterns
* Identify relevant features for property price prediction
* Train multiple machine learning regression models
* Compare model performance using standard evaluation metrics
* Predict the price of a new residential property
* Analyze the features that contribute most to price prediction

---

## 📊 Dataset

The original dataset contains **19,515 property records** and **12 attributes**.

### Target Variable

* `Price`

### Features Used for Model Training

* `Area`
* `BHK_Count`
* `Status`
* `Property Type`
* `Locality`
* `RERA Approval`
* `Flat Type`

### Feature Excluded from Modeling

`Rate per sqft` was excluded from model training because it is derived from the property's price and area. Including it could introduce **target leakage** and artificially improve model performance.

---

## 🧹 Data Preprocessing

The following preprocessing steps were performed:

1. Converted numerical columns to appropriate numeric formats.
2. Handled missing values in the target variable.
3. Removed duplicate records.
4. Removed records with invalid BHK values.
5. Applied percentile-based filtering to reduce the effect of extreme observations.
6. Selected relevant numerical and categorical features.
7. Standardized numerical features.
8. Applied One-Hot Encoding to categorical features.

### Dataset Reduction

| Stage                             | Number of Records |
| --------------------------------- | ----------------: |
| Original dataset                  |            19,515 |
| After removing missing Price      |            19,514 |
| After removing duplicates         |            14,222 |
| After removing invalid BHK values |            13,224 |
| Final dataset                     |        **12,759** |

---

## 🔍 Exploratory Data Analysis

Several visualizations were created to understand the dataset, including:

* Property price distribution
* Area vs. property price
* Average property price by BHK
* Top Gurgaon localities by number of properties
* Average property price by locality

The analysis showed that **property area is an important factor in determining property price**, while locality and property characteristics also contribute to price variation.

---

## 🤖 Machine Learning Models

Three regression models were trained and evaluated:

### 1. Linear Regression

A baseline regression model used to establish a relationship between the selected property features and price.

### 2. Random Forest Regression

An ensemble tree-based regression model capable of capturing nonlinear relationships between property characteristics and price.

### 3. Gradient Boosting Regression

A boosting-based regression model that builds an ensemble of decision trees sequentially.

---

## 📈 Model Evaluation

The models were evaluated using:

* **MAE (Mean Absolute Error)**
* **RMSE (Root Mean Squared Error)**
* **R² Score**

### Results

| Model             | MAE (₹ Crore) | RMSE (₹ Crore) |   R² Score |
| ----------------- | ------------: | -------------: | ---------: |
| Linear Regression |        0.6665 |         1.3787 |     0.8174 |
| Random Forest     |        0.5959 |         1.3597 | **0.8224** |
| Gradient Boosting |        1.0843 |         1.7129 |     0.7182 |

Based on the test-set results, the Random Forest model produced the highest R² score among the three models evaluated.

### Final Random Forest Performance

* **MAE:** ₹59.59 lakh
* **RMSE:** ₹1.36 crore
* **R² Score:** 0.8224

---

## 🏠 Sample Property Prediction

A sample property was used to demonstrate the prediction system.

### Property Details

| Feature       | Value         |
| ------------- | ------------- |
| Area          | 2,000 sq.ft   |
| BHK           | 3             |
| Status        | Ready to Move |
| Property Type | Apartment     |
| Locality      | Sector 57     |
| RERA Approval | Yes           |
| Flat Type     | Apartment     |

### Predicted Price

**Approximately ₹1.81 Crore**

This prediction demonstrates how the trained model can estimate the price of a property based on its characteristics.

---

## ⭐ Feature Importance

Feature importance analysis was performed using the trained Random Forest model.

The analysis showed that **Area** was the most influential feature in the trained model, followed by several locality and property-type features.

This provides an indication of which variables contributed most to the model's predictions.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Scikit-learn**
* **Joblib**
* **Google Colab**
* **Jupyter Notebook**
* **KaggleHub**

---

## 📁 Project Structure

```text
Gurgaon-Real-Estate-Price-Prediction/
│
├── Gurgaon_Real_Estate_Price_Prediction.ipynb
├── README.md
└── requirements.txt
```

### File Description

**Gurgaon_Real_Estate_Price_Prediction.ipynb**
Contains the complete Python implementation, data preprocessing, exploratory data analysis, model training, evaluation, predictions, and visualizations.

**README.md**
Provides documentation and an overview of the project.

**requirements.txt**
Contains the Python libraries required to run the project.

---

## 🔄 Project Workflow

```text
Dataset Collection
        ↓
Data Cleaning
        ↓
Exploratory Data Analysis
        ↓
Feature Selection
        ↓
Data Preprocessing
        ↓
Train-Test Split
        ↓
Model Training
        ↓
Model Evaluation
        ↓
Model Comparison
        ↓
Price Prediction
        ↓
Feature Importance Analysis
```

---

## 🚀 Future Scope

The project can be further improved by:

* Performing hyperparameter tuning
* Using larger and more recent real estate datasets
* Improving the handling of high-cardinality categorical features
* Developing a web-based property price prediction interface
* Deploying the model through an API
* Incorporating additional property and location attributes
* Performing time-based analysis of Gurgaon real estate prices
* Integrating regularly updated market data

---

## 👩‍💻 Author

**Akanksha Bharadwaj**

Software Development & Data Science Student

---

## 📌 Note

This project is developed for educational and internship purposes. The predicted prices are model estimates based on the dataset and features used during training and should not be considered professional property valuation.
