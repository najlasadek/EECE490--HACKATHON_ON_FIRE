# 🚬 **Smoking Intensity Prediction with Random Forest** 🚀

## 🌟 **Overview**
This project applies machine learning techniques to classify individuals into different smoking intensity levels based on survey data. By leveraging **Random Forest Classifiers**, we analyze feature importance, optimize the model, and explore the impact of feature reduction.

---

## 🎯 **Project Goals**
1. **Predict Smoking Intensity Levels**:
   - **0**: 10 or less cigarettes/day
   - **1**: 11 to 20 cigarettes/day
   - **2**: 21 to 30 cigarettes/day
   - **3**: 31 cigarettes/day or more
2. **Understand Feature Importance**:
   - Identify which attributes have the most significant impact on predictions.
3. **Compare Models**:
   - Full-feature model vs. Top 10 feature model.

---

## 🛠️ **Steps Taken**
### 1. **Data Loading**
- The dataset was sourced from **Google Sheets** and loaded via a CSV export link.

### 2. **Data Cleaning**
- Removed:
  - Unnamed columns (residuals from CSV export).
  - Duplicate columns.

### 3. **Data Preprocessing**
#### 🔢 **Target Encoding**:
- Converted smoking intensity levels into numerical classes:
  - `"10 or less cigarettes/day"` → `0`
  - `"11 to 20 cigarettes/day"` → `1`
  - `"21 to 30 cigarettes/day"` → `2`
  - `"31 cigarettes/day or more"` → `3`

#### 🔤 **One-Hot Encoding**:
- Transformed categorical variables into binary columns.
- Example:
  - `"Employment Status"` → `Employment Status_Employed`, `Employment Status_Unemployed`, etc.

#### ⚙️ **Feature Scaling**:
- Standardized numerical features using **z-score scaling** for zero mean and unit variance.

---

### 4. **Model Training**
- Trained a **Random Forest Classifier** using all features.
- Calculated **feature importance** to identify the top predictors.

### 5. **Feature Reduction**
- Selected the **top 10 features** based on importance.
- Retrained the model using only these features.

### 6. **Evaluation and Comparison**
- Metrics Used:
  - **Accuracy**
  - **Precision**
  - **Recall**
  - **F1-Score**
- Visualization:
  - **True vs. Predicted Class Plots**
  - **Confusion Matrices**

---

## 📊 **Results**
| Metric          | Original Model | Retrained Model |
|------------------|----------------|-----------------|
| **Accuracy**     | 62.79%         | 58.14%          |
| **Precision**    | 61.95%         | 60.73%          |
| **Recall**       | 62.79%         | 58.14%          |
| **F1-Score**     | 59.91%         | 58.62%          |

---

## 📌 **Key Observations**
1. **Original Model**:
   - Better overall performance with all features.
2. **Retrained Model**:
   - Simplified with the top 10 features but resulted in a slight drop in performance.
3. **Random Forest Limitations**:
   - While Random Forest is robust, it might not capture this dataset's complexities effectively.

---

## 💡 **Conclusion**
- **Random Forest** may not be the optimal choice for this problem.
- Performance can potentially improve with:
  - Advanced models like **Gradient Boosting Machines** (e.g., XGBoost, LightGBM).
  - Deep learning techniques for larger datasets.
  - Improved feature engineering and handling class imbalance.

---
