#  Physics Particle Classification Project

##  Project Overview
This project builds a complete machine learning pipeline to classify high-energy physics particles as either **signal (s)** or **background (b)**.  
The dataset contains particle measurements, and the task is to distinguish meaningful signal events from background noise — a common challenge in experimental physics.

---

##  Project Workflow

### **Phase 1: Data Understanding & Preparation**
- Loaded and cleaned raw particle physics dataset.
- Removed irrelevant columns (e.g., `EventId`).
- Handled missing values (`-999` replaced with mean/mode).
- Encoded labels: `signal (s)` → 1, `background (b)` → 0.
- Standardized features for fair model comparison.

### **Phase 2: Exploratory Data Analysis (EDA)**
- Visualized feature distributions across classes.
- Generated correlation heatmap to identify relationships.
- Checked target class distribution.

### **Phase 3: Preprocessing & Feature Engineering**
- Filled missing values.
- Label encoded categorical features.
- Scaled numerical features using **StandardScaler**.
- Split dataset into train (80%) and test (20%).

### **Phase 4: Model Training & Evaluation**
- Trained and evaluated multiple models:
  - Logistic Regression
  - Decision Tree
  - Random Forest
  - Gradient Boosting
  - Naive Bayes
- Used **Stratified K-Fold Cross-Validation** for robustness.
- Compared results (CV mean ± std vs. Test Accuracy).
- Overfitting reduced in **Logistic Regression** and **Naive Bayes** with stronger regularization.

### **Phase 5: Model Saving & Inference**
- Saved final model (`Random Forest`), scaler, and feature names.
- Implemented prediction function to classify new particle data.
- Example input predicted **background (b)** successfully.

---

## Results Summary

| Model              | CV Accuracy (± Std) | Test Accuracy |
|--------------------|----------------------|---------------|
| Logistic Regression | 0.9669 ± 0.0007      | 0.9679        |
| Decision Tree       | 1.0000 ± 0.0000      | 1.0000        |
| Random Forest       | 1.0000 ± 0.0000      | 1.0000        |
| Gradient Boosting   | 1.0000 ± 0.0000      | 1.0000        |
| Naive Bayes         | 0.9663 ± 0.0010      | 0.9658        |

- Final model: **Random Forest Classifier**  
- Predicted **background (b)** on test input.

---

## Conclusion
- We successfully built an end-to-end ML pipeline for particle classification.  
- Logistic Regression and Naive Bayes were regularized to reduce overfitting.  
- Tree-based models (Random Forest, Gradient Boosting) achieved perfect scores, reflecting dataset separability, though slight overfitting risk remains.  
- Final deployment used Random Forest for stable and robust predictions.

---

##  Tech Stack
- Python, Pandas, NumPy
- Scikit-Learn, XGBoost
- Matplotlib, Seaborn
- Joblib (model persistence)

---


