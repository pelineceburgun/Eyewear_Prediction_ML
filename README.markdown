# 🧠 Machine Learning Analysis for Eyewear and Emotion Prediction

This study performs three distinct classification tasks based on facial images:

1. **Gender Prediction**
2. **Emotion Prediction**
3. **Eyewear Prediction**

Different models were tested for each task, with hyperparameter optimization conducted, and the best results were analyzed.

---

## 👤 **Part 1 – Gender Prediction**

### 🎯 Objective

Predict whether a person is **male** or **female** (0: Male, 1: Female).

### 🔍 Models Tested

- **Logistic Regression (GridSearch)**  
  - Best: `C=1, penalty='l2'`  
  - **Train CV Accuracy**: 91.1%  
  - **Test Accuracy**: 93.3%  
- **SVC (GridSearch)**  
  - Best: `C=0.5, kernel='linear'`  
  - **Test Accuracy**: 95.5% ✅  
- **Random Forest**  
  - `max_depth=15` → **Test Accuracy**: 94.4%  
- **Gradient Boosting**  
  - **Test Accuracy**: 91.1%  
- **KNN**  
  - Best: `n_neighbors=3`, `weights='uniform'`, `metric='manhattan'`  
  - **Test Accuracy**: 90%  
- **PCA + Logistic Regression**  
  - **Test Accuracy**: 92.2%  

### 🥇 Best Model

✅ **SVC (Linear Kernel, C=0.5)**  
→ **Test Accuracy**: 95.5%

---

## 😊 **Part 2 – Emotion Prediction**

### 🎯 Objective

Predict the **emotional state** of a person from facial expressions (encoded as 0–6).

### 🔍 Models Tested

- **Logistic Regression**  
  - Best: `C=0.01, penalty='l1'`  
  - **Test Accuracy**: 58.9%  
- **SVC**  
  - Best: `kernel='rbf', C=0.1` → **Test Accuracy**: 62.2%  
- **Random Forest**  
  - `max_depth=15` → **Test Accuracy**: 64.4% ✅  
- **KNN**  
  - Best: `n_neighbors=9`, `metric='manhattan'`, `weights='uniform'`  
  - **Test Accuracy**: 55.6%  
- **Gradient Boosting**  
  - `max_depth=3` → **Test Accuracy**: 53.3%  
- **PCA + SVC**  
  - `kernel='linear'` → **Test Accuracy**: 53.3%  

### 🥇 Best Model

✅ **Random Forest (max_depth=15)**  
→ **Test Accuracy**: 64.4%  

🔍 **Note**: Emotion prediction is a more challenging task due to its multiclass nature and the complexity of facial expressions, resulting in lower accuracy.

---

## 🕶️ **Part 3 – Eyewear Prediction**

### 🎯 Objective

Predict whether a person is wearing **eyewear** (0: open eyes, 1: sunglasses).

### 🔍 Models Tested

- **Decision Tree**  
  - Best: `max_depth=3` → **Test Accuracy**: 63.3%  
- **Logistic Regression**  
  - Best: `C=0.1, penalty='l1'` → **Test Accuracy**: 68.9%  
- **SVC**  
  - Best: `kernel='poly', C=0.1` → **Test Accuracy**: 80% ✅  
- **Random Forest**  
  - Best: `max_depth=15` → **Test Accuracy**: 72.2%  
- **KNN**  
  - Best: `n_neighbors=5`, `weights='distance'`, `metric='euclidean'`  
  - **Test Accuracy**: 64.4%  
- **Gradient Boosting**  
  - **Test Accuracy**: 62.2%  
- **PCA + KNN**  
  - **Test Accuracy**: 63.3%  

### 🥇 Best Model

✅ **SVC (Poly Kernel, C=0.1)**  
→ **Test Accuracy**: 80%

---

## 📊 Comparison Table

| Task         | Best Model       | Test Accuracy |
|--------------|------------------|---------------|
| **Gender**   | SVC (linear)     | **95.5%** ✅   |
| **Emotion**  | Random Forest    | **64.4%**     |
| **Eyewear**  | SVC (poly)       | **80%** ✅     |

---

## 🧠 Results & Insights

- **Gender Prediction** achieved the highest accuracy due to the more distinct separation in the data.
- **Emotion Prediction** yielded lower accuracy due to the complexity of multiclass classification and ambiguous facial expressions.
- **Eyewear Prediction** benefited significantly from non-linear models like **SVC with polynomial kernel**.
- Model performance varies based on task complexity, data separability, and hyperparameter tuning.
- **GridSearch + Cross-validation** was highly effective in identifying optimal parameter combinations for each model.

---

## 🎯 Next Steps

- Apply **feature engineering** or **data augmentation** to enhance model performance.
- Evaluate models using additional metrics such as ROC AUC and Confusion Matrix.
- Test models with larger datasets.
- Compare results with deep learning approaches (e.g., CNN, Transfer Learning).