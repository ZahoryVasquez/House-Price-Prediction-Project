# 🏡 King County Housing Price Prediction

## 🚀 Project Overview
This project predicts **house prices** in King County using multiple machine learning models.  
The workflow covers **data preprocessing, feature selection, model building, and evaluation** to identify the most effective regression approach.  

The dataset provides detailed housing characteristics such as bedrooms, bathrooms, square footage, lot size, floors, waterfront, view, condition, grade, year built/renovated, and geographical location (zipcode, latitude, longitude).  

---

## 📂 Dataset  

**Source:** King County, USA (House Sales Data, 2014–2015)  
**Obtained from:** [Kaggle – King County House Sales Dataset](https://www.kaggle.com/datasets/minasameh55/king-country-houses-aa)  
**Description:** Contains detailed information on house sales in King County, including price, square footage, number of bedrooms and bathrooms, year built, condition, and location features.  
**Note:** The dataset was cleaned and preprocessed before model training to ensure consistency and interpretability.  

---

## 🧰 Methodology  

### 🔎 Data Preprocessing  
- Converted `date` into a **readable `YYYY-MM` format**.  
- Defined **target variable:** `price` (USD).  
- Selected relevant **features:** bedrooms, bathrooms, `sqft_living`, lot size, floors, `waterfront`, `view`, `condition`, `grade`, year built/renovated, `zipcode`, `lat`, `long`.  

### ✂️ Feature Selection & Refinement  
- **First iteration:** Removed low-correlated features (<50%).  
  - **Result:** Model performance decreased → these variables, although weakly correlated, contributed to non-linear interactions.  

- **Second iteration:** Dropped redundant variables while keeping key ones such as `latitude`.  
  - **Result:** Slight improvement in performance (~R² 0.76 with Linear Regression) and reduced dataset complexity.  

- **Overall:**  
  - Even though tree-based models like Random Forest and XGBoost can handle redundant variables, this refinement step was important to test the impact of feature reduction.  
  - It improved interpretability, reduced noise, and slightly boosted performance before hyperparameter tuning.  
  - Final performance gain came mainly from **tuning XGBoost**, but feature selection was an essential step in the model improvement process.  

---





     
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









---



---


---

## 🤖 Models & Performance  

1. **K-Nearest Neighbors (KNN) Regressor**  
   - Baseline model.  
   - R²: Train 0.35 | Test 0.25  

2. **Linear Regression**  
   - Simple linear approach.  
   - R²: Train 0.70 | Test 0.70  

3. **Random Forest Regressor** 🌳  
   - Captured non-linear relationships effectively.  
   - R²: Train 0.89 | Test 0.89  

4. **XGBoost Regressor** ⚡  
   - With hyperparameter tuning.  
   - R²: Train 0.987 | Test 0.908 ✅  

---

## 📊 Model Comparison  

### R² Scores on Test Set  

| Model               | R² (Test) |
|----------------------|-----------|
| KNN Regressor        | 0.25      |
| Linear Regression    | 0.70      |
| Random Forest        | 0.89      |
| XGBoost (tuned)      | 0.908     |

### 📉 Visualization  

![Model Comparison](results/model_comparison.png)

*The chart shows R² scores on the test set for each model, highlighting XGBoost as the top performer.*

---

## 📈 Key Insights  

- Feature refinement significantly impacted results: removing low-correlation features hurt predictive power, while dropping redundant but low-importance features slightly improved performance (~R² 0.76).  
- Tree-based models (Random Forest & XGBoost) outperformed KNN and Linear Regression due to their ability to capture complex, non-linear interactions.  
- Hyperparameter tuning of XGBoost delivered the strongest performance with R² ≈ 0.908 and RMSE ≈ 109K.  
- Simplifying the date variable improved both visualization (heatmaps) and model training without losing interpretability.  

---

## 📊 Metrics Explained  

- **MSE (Mean Squared Error):** Average squared prediction error (lower = better).  
- **RMSE (Root Mean Squared Error):** Interpretable error in housing price units.  
- **R² Score:** Proportion of variance explained by the model (closer to 1 = better).  

---

## 💡 Conclusion  

This project highlights the importance of **iterative feature selection** and **model tuning** in predictive analytics. While simpler models like Linear Regression provide a good baseline, ensemble methods (Random Forest, XGBoost) clearly outperform due to their ability to model complex patterns in housing markets. The final tuned XGBoost achieved the **best predictive accuracy (R² ~0.908, RMSE ~109K)**, showing strong potential for real-world applications in real estate valuation and investment analysis. Future improvements could include adding external datasets (e.g., interest rates, demographic factors) and exploring advanced deep learning methods for further performance gains.  

---

## ⚡ How to Run  

1. Clone the repo:  
```bash
git clone <your-repo-url>

