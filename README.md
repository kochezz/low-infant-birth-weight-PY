
# Low Infant Birth Weight Classification using Logistic Regression (Python)

[![Built With Python](https://img.shields.io/badge/Built%20With-Python-blue?logo=python)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status](https://img.shields.io/badge/Status-In%20Progress-orange)]()
[![Data](https://img.shields.io/badge/Data-Cleaned-lightgrey)]()

---

## 📘 Project Overview

This project applies **Logistic Regression** in **Python** to classify whether an infant’s birth weight is considered **low** based on various maternal and clinical factors. The dataset originates from a study conducted at **Baystate Medical Center**, Springfield, Massachusetts.

The goal is to:
- Train a predictive model using clinically relevant features.
- Evaluate performance across different classification thresholds.
- Visualize decision boundaries and ROC performance.
- Save and reuse the trained model.

---

## 📂 Repository Structure

```
APM_low_infant_birth_wt_PY/
├── data/
│   ├── raw/                   # Original 'BIRTH WEIGHT.csv'
│   ├── processed/             # Cleaned datasets and test/train splits
├── models/                    # Saved logistic regression model (.pkl)
├── notebooks/                 # Jupyter Notebooks for development
├── scripts/                   # Python scripts used for training and evaluation
├── reports/                   # Generated reports and visualizations
└── README.md                  # Project documentation
```

---

## 🔍 Dataset Summary

**Target Variable:**  
- `low`: 1 = Low birth weight, 0 = Not low

**Features Used in Model:**
- `age`, `lwt`, `race`, `smoke`, `ptl`, `ht`, `ui`, `ftv`

---

##  Model Development Summary

| Step                | Outcome                                                                 |
|---------------------|-------------------------------------------------------------------------|
| Data Cleaning       | Factor and binary conversion completed                                  |
| Train/Test Split    | 80/20 stratified using `train_test_split`                               |
| Model Type          | Logistic Regression (`sklearn.linear_model.LogisticRegression`)         |
| Threshold Strategy  | Evaluated at 0.3, 0.4, 0.55                                              |
| Model Export        | Saved as `logistic_model.pkl` in the `models/` directory                |

---

## 📊 Classification Threshold Comparison

| Threshold | Sensitivity | Specificity | Misclassification Rate |
|-----------|-------------|-------------|--------------------------|
| 0.30      | 0.50        | 0.73        | 0.34                     |
| 0.40      | 0.42        | 0.96        | 0.21                     |
| 0.55      | 0.08        | 1.00        | 0.29                     |

➡ **Recommended Threshold:** 0.40 (best balance between specificity and misclassification)

---

## 📈 ROC Curve & AUC

- **AUC:** 0.73  
- **Interpretation:** The model performs **significantly better than random guessing**, but further optimization is advised.

---

## 💾 Files Saved

- `logistic_model.pkl`: Serialized logistic regression model
- `test_data_predictions.csv`: Contains predictions and probabilities
- `birth_wt_clean.csv`: Cleaned and preprocessed dataset

---

## 🚀 Next Steps

- Handle class imbalance (e.g., SMOTE, undersampling)
- Explore ensemble models (Random Forest, XGBoost)
- Build interactive dashboards using Streamlit
- Deploy via REST API or web app for clinical simulation

---

## 📬 Contact

Developed by **Business Enterprise Data Architecture (BEDA)**  
📩 Email: [wphiri@beda.ie](mailto:wphiri@beda.ie)  
🔗 LinkedIn: [William Phiri](https://www.linkedin.com/in/william-phiri-866b8443/)  
🧭 _"Get it done the BEDA way"_

---

## 📄 License

This project is licensed under the MIT License.
