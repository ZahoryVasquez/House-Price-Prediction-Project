# 🏡 House Price Prediction Project

## 🚀 Overview
This project predicts **house prices** using multiple machine learning models. It explores **data preprocessing**, **feature selection**, and **model evaluation** to find the best regression approach.  

The dataset includes features like square footage, bedrooms, bathrooms, year built, and location coordinates. Special attention was given to the **`date` feature** for both visualization 📊 and modeling 🤖.

---

## 🛠️ Data Preprocessing
1. **📅 Date Handling:**  
   - Converted `date` into a **readable `YYYY-MM` format**.  
   - Encoded numerically with `OrdinalEncoder` for ML models.  

2. **🔍 Feature Selection & Improvements:**  
   - **First improvement:** Removed low-correlated columns (<50%) to simplify the dataset.  
   - **Second improvement:** Kept important features like latitude and removed others with redundancy.  

3. **⚖️ Scaling:**  
   - Applied standard scaling for numeric features where needed (e.g., KNN).

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
