# 📊 Crime-rate-prediction-model-comparison

A machine learning project focused on predicting crime rates using **regularized regression and ensemble learning techniques**. This project demonstrates end-to-end data processing, feature analysis, and model comparison on a high-dimensional real-world dataset.

---

## 🧠 Problem Statement

The dataset contains a large number of socio-economic variables with:

* High dimensionality
* Missing values
* Strong multicollinearity

👉 Objective:
Build a robust model to **predict crime rates** and identify key influencing factors.

---

## 📂 Dataset

**Communities and Crime Dataset**

* 100+ socio-economic features
* Target: Crime rate
* Includes missing values (`?`)

---

## 🔧 Data Processing Pipeline

* Removed non-informative identifier columns
* Handled missing values using **mean imputation**
* Applied **StandardScaler** for linear models
* Split data into training and testing sets

---

## 🚀 Project Highlights

### 🔹 Linear Regression (Baseline)

* A standard regression model that assumes a linear relationship between features and target.
* Used as a baseline to evaluate the effectiveness of more advanced techniques.
* Struggles with **multicollinearity and high-dimensional data**, leading to unstable predictions.

---

### 🔹 Ridge Regression (L2 Regularization)

* Adds an L2 penalty to shrink coefficients and reduce model variance.
* Helps mitigate **multicollinearity** by stabilizing coefficient estimates.
* Achieved significant performance improvement in this project, making it the **best linear model**.

---

### 🔹 LASSO Regression (L1 Regularization)

* Applies L1 penalty, forcing some coefficients to zero.
* Performs **automatic feature selection**, resulting in a sparse and interpretable model.
* Achieved performance comparable to Ridge while reducing feature complexity.

---

### 🔹 Principal Component Regression (PCR)

* Combines **PCA (dimensionality reduction)** with linear regression.
* Transforms original features into orthogonal components before modeling.
* Reduces dimensionality but may lose predictive information since PCA maximizes variance, not target relevance.

---

### 🔹 XGBoost (Extreme Gradient Boosting)

* An ensemble tree-based model that builds sequential decision trees to minimize error.
* Captures **non-linear relationships and feature interactions** effectively.
* Achieved the **best overall performance**, outperforming all linear models.

---

### 🔹 Key Techniques Applied

* **Feature Scaling (StandardScaler)**
  Essential for linear models with regularization to ensure fair coefficient penalization.

* **Handling Missing Values**
  Used mean imputation to handle incomplete data.

* **Hyperparameter Tuning**
  Applied GridSearchCV and LassoCV to optimize model parameters.

---

### 🏆 Key Outcome

> By combining regularization, dimensionality reduction, and ensemble learning, the project achieved **~98% reduction in prediction error**, demonstrating the importance of model selection and preprocessing in real-world datasets.

> Built and compared multiple regression models, achieving **~98% reduction in MSE** and identifying **XGBoost as the top-performing model**, while leveraging LASSO for feature selection and Ridge for stable modeling.

---

## 📊 Model Comparison

| Model                | Method Type              | Regularization | Feature Scaling | MSE ↓  | RMSE ↓ | Key Characteristics                                         |
| -------------------- | ------------------------ | -------------- | --------------- | ------ | ------ | ----------------------------------------------------------- |
| Linear Regression    | Baseline                 | None           | ❌ No            | 0.7897 | 0.8887 | Sensitive to multicollinearity, unstable in high dimensions |
| Ridge Regression     | Regularization (L2)      | L2             | ✅ Yes           | 0.0175 | 0.1325 | Strong baseline, stabilizes coefficients                    |
| LASSO Regression     | Regularization (L1)      | L1             | ❌ No            | 0.0178 | 0.1332 | Feature selection, sparse model                             |
| LASSO (Standardized) | Regularization (L1)      | L1             | ✅ Yes           | 0.0178 | 0.1334 | Similar performance, theoretically preferred                |
| PCR                  | Dimensionality Reduction | None           | ✅ Yes           | 0.0184 | 0.1356 | Uses PCA to reduce feature space                            |
| XGBoost              | Ensemble (Boosting)      | Implicit       | ❌ Not required  | 0.0158 | 0.1259 | Best performance, captures non-linear relationships         |

---

## 📌 Performance Summary

* **Baseline MSE:** 0.7897
* **Best Model:** XGBoost (0.0158) 
* **Overall Improvement:** ~98% MSE reduction

### Ranking (by MSE)

1. XGBoost 
2. Ridge Regression 
3. LASSO 
4. PCR

---

## 🧠 Key Insights

* **Regularization is essential** for high-dimensional data
* **Ridge Regression** effectively handles multicollinearity
* **LASSO** enables feature selection with minimal performance loss
* **PCR** reduces dimensionality but may lose predictive information
* **XGBoost outperforms all models** by capturing non-linear relationships

---

## 💡 Insight

> Combining proper preprocessing with advanced models enables significant performance gains.
> Tree-based methods (XGBoost) excel when non-linear patterns are present, while regularized linear models provide strong interpretability.

---

## 🏆 Final Conclusion

* 🥇 **Best accuracy:** XGBoost
* 🥈 **Best linear model:** Ridge Regression
* 🥉 **Best interpretability:** LASSO
* ⚖️ **Alternative approach:** PCR
* ❌ **Baseline limitation:** Linear Regression

---

## 🛠️ Tech Stack

* Python
* Pandas / NumPy
* Scikit-learn
* Matplotlib / Seaborn
* XGBoost

---

## 📦 Requirements

* Python 3.8+
* Jupyter Notebook

### 🔧 Libraries

```bash
pandas>=1.3
numpy>=1.21
matplotlib>=3.4
seaborn>=0.11
scikit-learn>=1.0
xgboost
jupyter
```

### 📥 Installation

```bash
pip install -r requirements.txt
```
---

## ▶️ How to Run

```bash
jupyter notebook
```

Open:

```
Regularized-Regression-on-Communities-and-Crime.ipynb
```

---

## 📌 What I Learned

* Handling noisy, high-dimensional real-world datasets
* Importance of **feature scaling and regularization**
* Trade-offs between **interpretability vs performance**
* Differences between:

  * Linear models
  * Regularization techniques
  * Dimensionality reduction
  * Ensemble methods

---

## 📁 Project Structure

```
.
├── notebooks/
│   └── Regularized-Regression-on-Communities-and-Crime.ipynb
├── data/
│   ├── communities.data
│   └── communities.names
├── requirements.txt
└── README.md
```

---

## 📎 Future Work

* Feature importance analysis (XGBoost / LASSO)
* Hyperparameter tuning for XGBoost
* Try additional models (e.g., LightGBM, Neural Networks)
* Cross-validation for more robust evaluation
