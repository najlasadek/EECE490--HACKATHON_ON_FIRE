# Smoking Intensity Prediction: Neural Networks and Random Forest

---

## **Overview**

This project explores predicting smoking intensity levels using **machine learning** and **deep learning techniques**, specifically:
1. **Random Forest Classifier**: To analyze feature importance and compare full-feature models to reduced-feature models.
2. **Neural Networks**: To experiment with architectures, hyperparameters, and epoch tuning for optimal performance.

The goal was to classify individuals into different smoking intensity levels based on survey data while understanding the role of key features in the prediction process.

---

## **Project Goals**

1. **Predict Smoking Intensity Levels**:
   - **0**: 10 or less cigarettes/day.
   - **1**: 11 to 20 cigarettes/day.
   - **2**: 21 to 30 cigarettes/day.
   - **3**: 31 cigarettes/day or more.
2. **Understand Feature Importance**:
   - Identify which attributes significantly impact predictions.
3. **Compare Models**:
   - Evaluate Random Forest vs. Neural Networks for the same problem.

---

## **Steps Taken**

### **Data Preprocessing**
1. **Data Cleaning**:
   - Removed unnecessary and duplicate columns.
   - Eliminated unnamed residual columns from CSV exports.
2. **Encoding**:
   - **Target Variable**: Mapped smoking intensity levels into numerical classes.
   - **One-Hot Encoding**: Transformed categorical variables into binary columns.
3. **Feature Scaling**:
   - Standardized numerical features using **z-score normalization**.
4. **Feature Selection**:
   - Identified the **most significant features** based on their correlation with the target variable to reduce dimensionality and improve model performance.

---

## **Random Forest Model**

### Steps:
1. **Full-Feature Model**:
   - Trained a **Random Forest Classifier** on all available features.
   - Calculated feature importance to identify predictors.
2. **Top 10 Features**:
   - Retrained the model using the top 10 most important features.

### Results:
| Metric          | Original Model | Retrained Model |
|------------------|----------------|-----------------|
| **Accuracy**     | 62.79%         | 58.14%          |
| **Precision**    | 61.95%         | 60.73%          |
| **Recall**       | 62.79%         | 58.14%          |
| **F1-Score**     | 59.91%         | 58.62%          |

#### Observations:
- The full-feature model outperformed the reduced-feature model.
- Random Forest struggled to fully capture the complexity of the data.

---

## **Neural Networks**

### Steps:
1. **Model Architectures**:
   - Designed multiple configurations, such as:
     - [(128, 0.3), (64, 0.3)].
     - [(256, 0.4), (128, 0.3), (64, 0.2)] (best configuration).
2. **Hyperparameter Tuning**:
   - Learning Rates: Tested 0.001, 0.005, 0.01.
   - Batch Sizes: Evaluated 16, 32, 64.
   - Epochs: Fixed at 50 for most experiments; fine-tuned for the best-fit model.
3. **Epoch Testing**:
   - For the best configuration, tested epoch counts (5, 10, 15, 23, 50) to find the optimal training duration.

### Results:
| **Best Configuration** | **Learning Rate** | **Batch Size** | **Test Loss** | **Test Accuracy** |
|-------------------------|-------------------|----------------|---------------|-------------------|
| [(256, 0.4), (128, 0.3), (64, 0.2)] | 0.001 | 64 | 0.7248 | 71.88% |

### Key Findings:
- **Best Epoch Count**: Validation accuracy peaked at **23 epochs**, ensuring optimal training without overfitting.
- Training beyond 23 epochs led to overfitting, as validation loss began increasing while accuracy plateaued.

---

## **Comparison: Random Forest vs. Neural Networks**

| **Metric**              | **Random Forest** | **Neural Networks** |
|--------------------------|-------------------|---------------------|
| **Best Accuracy**        | 62.79%            | 68%                 |
| **Feature Engineering**  | Crucial           | Crucial             |
| **Flexibility**          | Limited           | High                |
| **Overfitting Control**  | Strong            | Requires tuning     |

#### Observations:
- Neural networks outperformed Random Forest, especially after fine-tuning.
- Random Forest is robust but limited in capturing complex patterns compared to deep learning.

---

## **Conclusion**

This project demonstrates the power of systematic experimentation in machine learning and deep learning. By leveraging both Random Forest and Neural Networks:
1. **Neural Networks** achieved the best results with 71.88% accuracy, fine-tuned for 23 epochs.
2. **Random Forest** provided insights into feature importance but struggled to achieve competitive accuracy.

