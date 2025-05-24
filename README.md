# Low Birth Weight Prediction Project (Python)

This project applies logistic regression to predict low infant birth weight based on maternal and prenatal variables using Python.

---

## 📁 Project Structure

```
APM_low_infant_birth_wt_PY/
├── data/
│   ├── raw/
│   │   └── birth_wt_clean.csv
│   ├── processed/
│   │   ├── train_data.csv
│   │   └── test_data.csv
├── models/
│   └── logit_model.pkl
├── notebooks/
│   └── 01_modeling.ipynb
├── outputs/
│   └── visualizations/
├── .env
└── README.md
```

---

## 🧪 Objective

To predict whether an infant's birth weight is low using maternal characteristics and clinical data.

**Target Variable**:  
- `low` (1 = Low birth weight, 0 = Not low)

**Predictors**:  
- `age`: Mother’s age  
- `lwt`: Weight at last menstrual period  
- `race`: (White, Black, Other)  
- `smoke`: Smoked during pregnancy  
- `ptl`: Premature labor history  
- `ht`: Hypertension history  
- `ui`: Uterine irritability  
- `ftv`: First trimester physician visits  

---

## 🧹 Data Processing

- Removed identifiers: `sr_no`, `id`
- Encoded categorical features
- Saved cleaned dataset to `processed/` directory

---

## 📊 Exploratory Data Analysis (EDA)

- Faceted visualizations were used to explore trends.
- Smoking, hypertension, and uterine irritability were linked to higher low birth weight risks.
- Distributions of age and weight (lwt) were examined for trends by target class.

---

## 🧠 Model Building

Model: Logistic Regression (via `sklearn`)  
Train-test split: 80/20 (random state 123)  
Performance measured on test set

---

## 📈 Evaluation

**Threshold Evaluation Summary**:

| Threshold | Sensitivity | Specificity | Misclassification |
|-----------|-------------|-------------|--------------------|
| 0.30      | 0.50        | 0.73        | 0.34               |
| 0.40      | 0.42        | 0.96        | 0.21               |
| 0.55      | 0.08        | 1.00        | 0.29               |

- **Recommended Cutoff**: 0.40 based on better trade-off between true positive and false positive rates in this test split.
- **ROC AUC Score**: 0.73 (Moderate discriminative power)

---

## 💾 Model Saving

Trained model saved as `logit_model.pkl`:
```python
import joblib
joblib.dump(logit_model, 'models/logit_model.pkl')
```

---

## 🧭 Insights

- Logistic regression yielded moderate accuracy.
- Feature `smoke`, `race`, and `ht` had stronger influence based on model coefficients.
- Threshold selection affected sensitivity and specificity balance.
- Results slightly differ from the R project due to different train-test partitions.

---

## 👨‍💻 Author

**William C. Phiri**  
🔗 [GitHub](https://github.com/kochezz) | [LinkedIn](https://www.linkedin.com/in/william-phiri-866b8443/)

---

_Last updated: May 24, 2025_
