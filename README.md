# 🏡 King County Housing Price Prediction

## 🚀 Project Overview
This project predicts **house prices** in King County using multiple machine learning models.  
The workflow covers **data preprocessing, feature selection, model building, and evaluation** to identify the most effective predictive modeling approach.  

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

**Overall:**  
  - After comparing several models (KNN, Linear Regression, Random Forest, and XGBoost), **XGBoost** was selected as the best price predictor.  
  - The feature selection strategy was applied to this model to test whether reducing redundant variables could bring improvements.  
  - Although XGBoost can handle redundant variables, this step helped enhance interpretability, reduce noise, and provide more stability before tuning.  
  - The biggest performance boost came from **tuning XGBoost**, but feature refinement was key as a prior optimization step.  

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
   - **Improved once with hyperparameter tuning**.   
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

---

## 📂 Key Insights
- Simplifying the date variable improved both visualization (heatmaps) and model training without losing interpretability.  
- Tree-based models (Random Forest & XGBoost) outperformed KNN and Linear Regression due to their ability to capture complex, non-linear interactions.
- Feature refinement significantly impacted results: removing low-correlation features hurt predictive power, while dropping redundant but low-importance features slightly improved performance (~R² 0.76).  
- Hyperparameter tuning of XGBoost delivered the strongest performance with R² ≈ 0.908 and RMSE ≈ 109K.  

---

## 📊 Metrics Explained
- **MSE (Mean Squared Error):** Lower is better; measures average squared error.  
- **RMSE (Root Mean Squared Error):** Square root of MSE; easier to interpret in house price units.  
- **R² Score:** Proportion of variance explained; closer to 1 = better prediction.

---

## 💡 Conclusion  

This project highlights the importance of **iterative feature selection** and **model tuning** in predictive analytics. While simpler models like Linear Regression provide a good baseline, ensemble methods (Random Forest, XGBoost) clearly outperform due to their ability to model complex patterns in housing markets. The final tuned XGBoost achieved the **best predictive accuracy (R² ~0.908, RMSE ~109K)**, showing strong potential for real-world applications in real estate valuation and investment analysis. Future improvements could include adding external datasets (e.g., interest rates, demographic factors) and exploring advanced deep learning methods for further performance gains.  

---

## 🙋🏽‍♀️ About Me

- Rocío Zahory Vásquez Romero
- Senior Auditor | Data Science & Machine Learning Enthusiast
- Email: rocio.vasquez@usach.cl
- LinkedIn: https://www.linkedin.com/in/rocio-zahory-vasquez-romero-3621ab1a7/


## ⚡ How to Run
1. Clone the repo:  
```bash
git clone <your-repo-url>







