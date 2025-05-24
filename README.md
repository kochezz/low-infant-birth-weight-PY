
# Low Infant Birth Weight Prediction (Python)

[![Built With](https://img.shields.io/badge/Built%20With-Python-blue)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status](https://img.shields.io/badge/Status-In%20Progress-orange)]()
[![Data](https://img.shields.io/badge/Data-Cleaned-lightgrey)]()

## Overview

This project aims to develop a logistic regression model in Python to predict the likelihood of low infant birth weight using a dataset containing demographic and clinical features. It is a follow-up to an R-based version of the same analysis.

## Dataset

The dataset contains 189 records with variables including:
- `age`: Age of the mother
- `lwt`: Weight at last menstrual period
- `race`: Race (1 = White, 2 = Black, 3 = Other)
- `smoke`: Smoking status (1 = Yes, 0 = No)
- `ptl`: Number of premature labors
- `ht`: History of hypertension (1 = Yes, 0 = No)
- `ui`: Uterine irritability (1 = Yes, 0 = No)
- `ftv`: Number of physician visits in the first trimester
- `low`: Target variable indicating if the birth weight was low

## Workflow

1. **Data Loading**  
   Data was pulled from a PostgreSQL database hosted on Neon.tech.

2. **EDA & Cleaning**  
   - Initial profiling using pandas and seaborn
   - Visualizations using `seaborn` and `matplotlib`
   - Converted categorical features to binary/factor levels

3. **Modeling**  
   - Fitted logistic regression model using `scikit-learn`
   - Evaluated with accuracy, precision, recall, and F1-score
   - Compared predictions with classification thresholds: 0.3, 0.4, 0.55
   - ROC curve and AUC calculated to assess discriminative ability

4. **Insights**  
   - `smoke`, `race`, `ht`, and `ui` were the most influential variables
   - Optimal threshold based on misclassification rate: **0.4**
   - AUC ≈ 0.73 suggests moderate model performance

5. **Model Export**  
   Saved using `joblib` for future deployment

## Directory Structure

```
├── data
│   ├── raw
│   │   └── birth_wt_clean.csv
│   └── processed
├── notebooks
│   └── analysis.ipynb
├── models
│   └── birth_wt_model.pkl
├── scripts
│   └── utils.py
└── README.md
```

## Setup

```bash
# Clone the repository
git clone https://github.com/kochezz/low-infant-birth-weight-PY.git

# Navigate into the project directory
cd low-infant-birth-weight-PY

# Install requirements
pip install -r requirements.txt
```

## License

This project is licensed under the MIT License.
