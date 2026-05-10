# Machine Learning Pipeline

```mermaid
flowchart TD
    A([📂 Raw Data\ninmate_dashboard.xlsx]) --> B[Data Loading\npandas · openpyxl]
    B --> C[Exploratory Data Analysis\nDistributions · Correlations · Trends]
    C --> D[Feature Engineering\nLabel Encoding · Scaling · Train/Test Split]

    D --> E1[🔵 Notebook 1\nRegression\nTarget: release_days]
    D --> E2[🟠 Notebook 2\nTime Series\nTarget: booking volume]
    D --> E3[🔴 Notebook 3\nClassification\nTarget: risk_flag]

    E1 --> F1[Linear Regression\nRidge · Random Forest\nXGBoost]
    E2 --> F2[ARIMA 2,1,2\nRolling Averages\nOvercrowding Flags]
    E3 --> F3[Logistic Regression\nRandom Forest Classifier]

    F1 --> G1[MAE · RMSE · R²\nCross-Validation]
    F2 --> G2[Forecast Plot\nConfidence Intervals\nRisk Threshold]
    F3 --> G3[Accuracy · Precision\nRecall · ROC-AUC\nConfusion Matrix]

    G1 --> H[📊 Feature Importance\nModel Selection]
    G3 --> H
    G2 --> I[📅 30-Day Outlook\nCapacity Planning]

    H --> J[⚖️ Fairness Audit\nSubgroup Analysis]
    J --> K([✅ Decision Support\nOutput for Administrators])
    I --> K

    style A fill:#2C3E50,color:#fff
    style K fill:#27AE60,color:#fff
    style E1 fill:#2980B9,color:#fff
    style E2 fill:#E67E22,color:#fff
    style E3 fill:#C0392B,color:#fff
    style J fill:#8E44AD,color:#fff
```

> **Note:** All three notebooks feed into a unified decision-support layer. No model output is used as a standalone decision — all predictions are reviewed by corrections professionals.
