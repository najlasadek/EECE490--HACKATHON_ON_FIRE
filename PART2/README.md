# README: Smoking Intensity Prediction Using Neural Networks

---

## **Project Overview**

This project explores predicting smoking intensity levels using survey data by designing and optimizing **neural networks**. The process involved systematic experimentation with various architectures, batch sizes, learning rates, and epoch counts to identify the best-performing model configuration.

---

## **What I Did**

1. **Data Preprocessing**:
   - Removed unnecessary and duplicate columns from the dataset.
   - Encoded binary and categorical variables using **one-hot encoding**.
   - Mapped the target variable (`smoking intensity`) into numerical categories:
     - **0**: 10 or less cigarettes/day.
     - **1**: 11 to 20 cigarettes/day.
     - **2**: 21 to 30 cigarettes/day.
     - **3**: 31 or more cigarettes/day.
   - Scaled the input features using **z-score normalization** to ensure better convergence during training.
   - Selected the **most significant features** based on their correlation with the target variable to reduce dimensionality and improve model performance.

2. **Model Architectures**:
   - Designed multiple neural network architectures with varying:
     - Number of layers (depth).
     - Neuron configurations.
     - Dropout rates for regularization.
   - Used **ReLU activation** in hidden layers and a **softmax activation** in the output layer to classify the target variable into four categories.

3. **Hyperparameter Tuning**:
   - Experimented with various combinations of:
     - **Learning Rates**: Tested values of 0.001, 0.005, and 0.01.
     - **Batch Sizes**: Evaluated 16, 32, and 64.
     - **Epochs**: Fixed at 50 epochs for most configurations, except the best-fit model, where epoch count was fine-tuned.

4. **Model Evaluation**:
   - **Validation Loss** and **Validation Accuracy** were used during training to monitor overfitting.
   - **Test Loss** and **Test Accuracy** measured generalization on unseen data.
   - **Classification Report** and **Confusion Matrix** provided insights into per-class performance and misclassifications.

---

## **Experimental Results**

### **Best Configuration**
| **Architecture**                     | **Learning Rate** | **Batch Size** | **Test Loss** | **Test Accuracy** |
|--------------------------------------|-------------------|----------------|---------------|-------------------|
| [(256, 0.4), (128, 0.3), (64, 0.2)]  | 0.001             | 64             | 0.7248        | 71.88%            |

The best configuration achieved a **test accuracy of 71.88%** with a **loss of 0.7248**. This architecture provided the best balance of depth and regularization among all configurations tested.

### **Other Configurations**
| **Architecture**       | **Learning Rate** | **Batch Size** | **Test Loss** | **Test Accuracy** |
|-------------------------|-------------------|----------------|---------------|-------------------|
| [(128, 0.3), (64, 0.3)]| 0.001             | 16             | 0.7537        | 65.62%            |
| [(128, 0.3), (64, 0.3)]| 0.005             | 64             | 1.2339        | 62.50%            |
| [(256, 0.4), (128, 0.3), (64, 0.2)]| 0.005 | 16             | 1.6168        | 56.25%            |
| [(64, 0.2), (32, 0.2)] | 0.01              | 32             | 1.4824        | 59.38%            |

---

## **Testing the Number of Epochs**

After identifying the best-fit configuration:
- **Architecture**: [(256, 0.4), (128, 0.3), (64, 0.2)]
- **Learning Rate**: 0.001
- **Batch Size**: 64

We fine-tuned the number of epochs by evaluating the model at different values (**5, 10, 15, 25, 50**) to determine the optimal training duration.

### Key Findings:
- The best performance was achieved at **23 epochs**, where:
  - Validation accuracy peaked (~71.88%).
  - Validation loss was minimized, ensuring the model generalized well to unseen data.
- Training beyond 12 epochs led to overfitting, as validation loss began increasing while accuracy plateaued.
---

## **Conclusion**

This project highlights the importance of systematic experimentation with architectures, hyperparameters, and training strategies. By selecting the most significant features and optimizing hyperparameters like batch size and learning rate, the model achieved a test accuracy of **71.88%**. While this is a significant step forward, further improvements in feature engineering, optimization techniques, and alternative modeling approaches are necessary to achieve even better results. 🚀
