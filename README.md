# 🏡 King County Housing Price Prediction

## 🚀 Overview
This project predicts **house prices** using multiple machine learning models. It explores **data preprocessing**, **feature selection**, and **model evaluation** to find the best regression approach.  

The dataset includes features like square footage, bedrooms, bathrooms, year built, and location coordinates. Special attention was given to the **`date` feature** for both visualization 📊 and modeling 🤖.

This project predicts **house sale prices** in **King County, Washington** (21,613 sales, 2014–2015).
We explored the data, identified key drivers of price, and tested multiple machine learning models.
**Goal:** Find the best model for accurate price prediction and understand which features matter most.


##📂 Dataset

Source: King County, USA (House Sales Data)
Obtained from: Kaggle - King County House Sales Dataset
Description: Contains detailed information on house sales in King County, including price, square footage, number of bedrooms and bathrooms, year built, condition, and location features. This dataset is commonly used for regression analysis and predictive modeling.

---

## 🛠️ Data Preprocessing
1. **📅 Date Handling:**  
   - Converted `date` into a **readable `YYYY-MM` format**.  

2. **🔍 Feature Selection & Improvements:**  
   - **First improvement:** Removed low-correlated columns (<50%) to simplify the dataset.  
   - **Second improvement:** Kept important features like latitude and removed others with redundancy.
     
---

## 🧰 Models Used
1. **K-Nearest Neighbors (KNN) Regressor**  
   - Baseline regression model.  
   - R²: Train 0.35 | Test 0.25  

2. **Linear Regression**  
   - Simple linear approach.  
   - R²: Train 0.70 | Test 0.70  

3. **Random Forest Regressor** 🌳  
   - Captures non-linear patterns with ensemble trees.  
   - R²: Train 0.89 | Test 0.89  

4. **XGBoost Regressor** ⚡  
   - **Improved once with hyperparameter tuning**.  
   - R²: Train 0.987 | Test 0.908 ✅  

---

## 📈 Key Insights
- Data improvements were crucial: **2 rounds of feature refinement** increased predictive power.  
- Tree-based models (Random Forest & XGBoost) outperform KNN and Linear Regression due to their ability to model complex relationships.  
- The simplified date format works for both **heatmaps** and **ML models** without losing interpretability.  

---

## 📊 Metrics Explained
- **MSE (Mean Squared Error):** Lower is better; measures average squared error.  
- **RMSE (Root Mean Squared Error):** Square root of MSE; easier to interpret in house price units.  
- **R² Score:** Proportion of variance explained; closer to 1 = better prediction.

---

## ⚡ How to Run
1. Clone the repo:  
```bash
git clone <your-repo-url>


## 🙋🏽‍♀️ About Me

Rocío Zahory Vásquez Romero

Senior Auditor | Data Science & Machine Learning Enthusiast
Email: rocio.vasquez@usach.cl
LinkedIn: https://www.linkedin.com/in/rocio-zahory-vasquez-romero-3621ab1a7/






---
## :open_file_folder: Dataset
- **Target:** `price` (USD)
- **Features:** bedrooms, bathrooms, `sqft_living`, lot size, floors, `waterfront`, `view`, `condition`, `grade`, year built/renovated, `zipcode`, `lat`, `long`
---
## :gear: Workflow
1. **Data Cleaning**: handled duplicates, converted dates, removed irrelevant columns.
2. **EDA**: histograms, boxplots, correlation heatmaps.
   - Top drivers: `sqft_living`, `grade`, `sqft_above`, `sqft_living15`.
   - For expensive homes (≥ $650k), **size** and **grade** matter most.
3. **Models Tested**:
   - KNN → poor generalization (R² ~0.25)
   - Linear Regression → decent baseline (R² ~0.70)
   - Random Forest → strong (R² ~0.89, RMSE ~114k)
   - XGBoost → best baseline (R² ~0.897, RMSE ~111k)
4. **Improvements**:
   - Dropping low-correlation features hurt performance.
   - Dropping low-importance features improved slightly (R² ~0.76).
   - **Hyperparameter tuning of XGBoost** → best result (R² ~0.908, RMSE ~109k).
---
## :bar_chart: Results
| Model              | RMSE (USD) | R²   |
|--------------------|------------|------|
| KNN                | ~300k      | 0.25 |
| Linear Regression  | 200–360k   | 0.70 |
| Random Forest      | 114k       | 0.89 |
| XGBoost (baseline) | 111k       | 0.897|
| **XGBoost (tuned)**| **109k**   | **0.908** |
**Key Insight:** Tree-based models (RF, XGBoost) dramatically outperform simpler baselines.
The tuned XGBoost is the final model, explaining ~91% of price variability.
