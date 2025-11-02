
# 🧠 Titanic Dataset Feature Engineering

## 📊 Overview
This repository contains data preprocessing and feature engineering steps performed on the **Titanic Survival Dataset**.  
The goal is to prepare clean, transformed data suitable for machine learning classification tasks.

---

## 📂 Dataset
- **Source:** [Kaggle - Titanic: Machine Learning from Disaster](https://www.kaggle.com/c/titanic)
- **Type:** Classification (Predict survival: 1 = Survived, 0 = Not Survived)
- **Size:** 891 rows × 12 columns

---

## ⚙️ Steps Performed

### 1. Data Loading & Exploration
- Loaded dataset using `pandas`
- Checked for missing values and data types
- Explored distribution of numerical & categorical features

### 2. Missing Value Handling
| Column | Action |
|---------|---------|
| Age | Filled with median |
| Embarked | Filled with mode |
| Cabin | Dropped (too many missing values) |

Reason: Prevents model errors from NaN values and retains dataset integrity.

### 3. Encoding Categorical Variables
- **Label Encoding** for `Sex`
- **One-Hot Encoding** for `Embarked`

Reason: Converts categorical data to numeric values suitable for ML algorithms.

### 4. Feature Scaling
- Applied **StandardScaler** to numeric features (`Age`, `Fare`)
- Ensures all numeric values have zero mean and unit variance

### 5. Dimensionality Reduction (PCA)
- Applied PCA to visualize relationships between numeric features
- Reduced redundancy and improved interpretability

### 6. Feature Selection
- Used **SelectKBest (chi²)** to select top 5 predictive features
- Selected features: `Pclass`, `Sex`, `Fare`, `Age`, `Embarked_S`

---

## 📈 Observations
- Females had higher survival chances than males.  
- Higher class (Pclass 1) passengers had greater survival probability.  
- Fare positively correlated with survival likelihood.  
- PCA components explained most data variance.  
- Final dataset is clean, numeric, and ready for ML modeling.

---

## ⚖️ Ethical Considerations
If this model were used for **real-world predictions** (e.g., employee attrition or credit scoring):
- Gender and Marital Status could introduce **algorithmic bias**.
- Models may unintentionally discriminate against certain groups.

### ✅ Mitigation Steps
1. Exclude sensitive features unless justified.  
2. Evaluate bias using fairness metrics (e.g., equal opportunity).  
3. Use fairness toolkits (IBM AIF360, Fairlearn).  
4. Maintain transparency in data usage.

---

## 🧩 Files Included
- `Titanic_Data_Preprocessing.ipynb` — Complete Jupyter Notebook
- `Titanic_Feature_Engineering_Report.pdf` — Summary report
- `README.md` — Project documentation

---

