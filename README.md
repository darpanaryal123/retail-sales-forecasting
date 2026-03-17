# Retail Sales Forecasting Engine

> Time-series forecasting with XGBoost/ARIMA ensemble · 3.2% MAE · Power BI dashboard

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-189AB4?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)

---

## Problem Statement

Retail businesses lose significant revenue to overstocking and stockouts. Accurate demand forecasting enables smarter inventory planning. This project builds a production-grade forecasting engine comparing statistical and ML approaches, then delivers results through an interactive Power BI dashboard.

---

## Results

| Model | MAE | RMSE | Notes |
|---|---|---|---|
| ARIMA (baseline) | 4.1% | 5.3% | Strong on seasonal patterns |
| XGBoost | 3.8% | 4.9% | Strong on non-linear relationships |
| **ARIMA + XGBoost Ensemble** | **3.2%** | **4.1%** | **22% improvement over client baseline** |

---

## Approach

### 1. Data Processing
- 100,000+ rows of retail transaction data
- Handled missing values, outliers, and seasonal decomposition
- Created lag features (7-day, 14-day, 30-day), rolling statistics, and holiday flags

### 2. Model Development
- **ARIMA**: Tuned `(p,d,q)` parameters using AIC/BIC grid search
- **XGBoost**: Hyperparameter optimization via cross-validated grid search
- **Ensemble**: Weighted average combining both model outputs

### 3. Evaluation
- Train/test split respecting temporal order (no data leakage)
- Metrics: MAE, RMSE, MAPE
- Residual analysis for each model

### 4. Dashboard
- Interactive Power BI dashboard for inventory planning
- Scenario simulation: adjust inputs and see forecast impact
- Exportable weekly/monthly demand summaries

---

## Tech Stack

| Component | Technology |
|---|---|
| Language | Python 3.10+ |
| Data processing | Pandas, NumPy |
| Statistical model | Statsmodels (ARIMA) |
| ML model | XGBoost, Scikit-Learn |
| Visualization | Matplotlib, Seaborn, Power BI |
| Notebook | Jupyter |

---

## Project Structure

```
retail-sales-forecasting/
├── data/
│   └── sample_data.csv           # Sample dataset (anonymized)
├── notebooks/
│   ├── 01_eda.ipynb              # Exploratory data analysis
│   ├── 02_preprocessing.ipynb    # Feature engineering
│   ├── 03_arima.ipynb            # ARIMA modelling
│   ├── 04_xgboost.ipynb          # XGBoost modelling
│   └── 05_ensemble.ipynb         # Ensemble and evaluation
├── src/
│   ├── preprocess.py             # Data cleaning pipeline
│   ├── arima_model.py            # ARIMA model class
│   ├── xgboost_model.py          # XGBoost model class
│   └── ensemble.py               # Ensemble logic
├── dashboard/
│   └── retail_dashboard.pbix     # Power BI dashboard file
├── requirements.txt
└── README.md
```

---

## Setup & Run

```bash
git clone https://github.com/darpanaryal/retail-sales-forecasting.git
cd retail-sales-forecasting
pip install -r requirements.txt

# Run full pipeline
jupyter notebook notebooks/01_eda.ipynb
```

---

## Author

**Darpan Aryal** · [LinkedIn](https://linkedin.com/in/darpanaryal) · [aryaldarpan20@gmail.com](mailto:aryaldarpan20@gmail.com)
