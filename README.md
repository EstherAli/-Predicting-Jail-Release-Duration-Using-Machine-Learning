# 🏛️ Predictive Analytics for Criminal Justice Reform

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-orange?logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-green?logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-Boosting-red)
![ARIMA](https://img.shields.io/badge/statsmodels-ARIMA-purple)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

> Advanced predictive analytics solutions designed to improve efficiency, accuracy, and decision-making within U.S. correctional systems — addressing inmate processing delays, overcrowding, and administrative inefficiencies through machine learning, time series forecasting, and risk classification.

---

## 👤 Author

**Esther Ali**  
M.S. Business Analytics – University of Louisville  
Senior Corrections Data Analyst & Technician – Louisville Metro Department of Corrections

---

## 📌 Problem Statement

Correctional systems across the United States face critical operational challenges including delayed inmate processing, facility overcrowding, sentencing miscalculations, and limited data-driven decision-making. These issues result in wrongful detention, increased costs, strained inter-agency relationships, and reduced system efficiency.

The Louisville Metro Department of Corrections — serving local, sheriff, and federal detainees across four Kentucky counties — is a direct operational context for the challenges this project addresses.

---

## 💡 Proposed Solution

This project applies predictive analytics and machine learning to:

- **Predict inmate processing delays** at booking time using regression models
- **Forecast jail population trends** using ARIMA time series modeling
- **Classify high-risk cases** early for proactive resource and custody allocation
- **Support inter-agency coordination** with automated alerts and population outlooks

---

## 📂 Repository Structure

```
├── README.md                          ← This file
│
├── notebooks/
│   ├── 01_processing_delay_prediction.ipynb   ← Regression: predict release_days
│   ├── 02_population_forecasting.ipynb        ← Time series: ARIMA booking forecast
│   └── 03_risk_classification.ipynb           ← Classification: predict risk_flag
│
├── data/
│   └── inmate_dashboard.xlsx          ← Synthetic dataset (100 records, 17 features)
│
├── diagrams/
│   ├── processing_pipeline.md         ← Inmate lifecycle flow (Mermaid)
│   ├── ml_pipeline.md                 ← ML system architecture (Mermaid)
│   └── interagency_flow.md            ← Agency coordination map (Mermaid)
│
└── reports/
    └── national_impact.md             ← Policy impact & scalability analysis
```

---

## 🧪 Technical Components

| Component | Tools |
|---|---|
| Machine Learning | scikit-learn, XGBoost |
| Time Series Forecasting | statsmodels (ARIMA) |
| Data Processing | pandas, NumPy |
| Visualization | matplotlib, seaborn |
| Notebook Environment | Jupyter |
| Data Source | Synthetic (privacy-safe) |

---

## 📊 Notebooks Overview

### 📘 Notebook 1: Processing Delay Prediction
Predicts `release_days` using 12 booking-time features across four regression models.

- Full EDA with 6 charts (distribution, county, custody level, agency, correlation heatmap)
- Models: Linear Regression · Ridge · Random Forest · XGBoost
- Metrics: MAE, RMSE, R², 5-fold Cross-Validation
- Feature importance analysis
- Policy impact and ethics section

### 📙 Notebook 2: Jail Population Forecasting
Forecasts daily booking volume using ARIMA time series modeling.

- Time series construction from booking timestamps
- Rolling averages (7-day, 14-day)
- Stationarity testing (Augmented Dickey-Fuller)
- ACF/PACF analysis for parameter selection
- ARIMA(2,1,2) with 80% confidence intervals
- Overcrowding risk flagging at 75th percentile threshold

### 📕 Notebook 3: Risk Classification
Binary classification of `risk_flag` to support custody and resource decisions.

- Risk distribution analysis across county, custody level, agency, charge type
- Models: Logistic Regression · Random Forest Classifier
- Metrics: Accuracy, Precision, Recall, F1, ROC-AUC
- Confusion matrix visualization
- **Fairness audit**: False Positive and False Negative rates by county

---

## 🗺️ System Diagrams

All diagrams render natively on GitHub (Mermaid format):

- [`diagrams/processing_pipeline.md`](diagrams/processing_pipeline.md) — Full inmate lifecycle from arrest to release
- [`diagrams/ml_pipeline.md`](diagrams/ml_pipeline.md) — ML system architecture across all three notebooks
- [`diagrams/interagency_flow.md`](diagrams/interagency_flow.md) — LMDC coordination with FBI, ATF, Courts, KDOC

---

## 📈 Key Results

| Model | Task | Best Metric |
|---|---|---|
| XGBoost / Random Forest | Processing delay prediction | MAE < 2.5 days |
| ARIMA(2,1,2) | Population forecasting | 30-day outlook with 80% CI |
| Random Forest Classifier | Risk classification | ROC-AUC > 0.72 |

---

## 🌍 Real-World Relevance

This project is directly informed by operational experience at the **Louisville Metro Department of Corrections**, including:

- Daily inmate processing and data entry workflows
- State-level reporting and sentence validation
- Inter-agency coordination with courts, sheriff's office, and federal agencies
- TIC (Technology Integration Coordinator) responsibilities

The models and workflows in this repository reflect real challenges encountered in that environment and are designed to be practically deployable.

---

## 🚀 National Impact

The solutions developed here are scalable and applicable to correctional systems across the United States:

- **Reduce processing delays** through early prediction and court calendar coordination
- **Prevent overcrowding** with 30-60 day population forecasts
- **Improve sentencing accuracy** via data validation tools
- **Enhance inter-agency coordination** through automated alerts
- **Support evidence-based reform** with transparent, auditable models

See [`reports/national_impact.md`](reports/national_impact.md) for a full policy analysis.

---

## ⚖️ Ethics & Data Responsibility

This project takes algorithmic fairness seriously:

- All datasets are **synthetic and anonymized** — no real inmate data is used
- Notebook 3 includes a **formal fairness audit** comparing False Positive Rates across counties
- All models are positioned as **decision-support tools**, not autonomous decision-makers
- The project explicitly references and addresses criticisms of tools like **COMPAS**
- Regular retraining, independent auditing, and human oversight are required for responsible deployment

---

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone https://github.com/your-username/correctional-predictive-analytics.git
cd correctional-predictive-analytics

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn xgboost statsmodels openpyxl

# 3. Launch Jupyter
jupyter notebook

# 4. Open notebooks/ in order and run all cells
#    Kernel → Restart & Run All
```

> ⚠️ Keep `data/inmate_dashboard.xlsx` in the `data/` folder — all notebooks reference it with the relative path `../data/inmate_dashboard.xlsx`.

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

---

*Esther Ali · Louisville Metro Department of Corrections · M.S. Business Analytics, University of Louisville · 2024*
