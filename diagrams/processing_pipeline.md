# Processing Pipeline

```mermaid
flowchart LR
    A([👤 Arrest]) --> B[Booking & Intake]
    B --> C[Data Entry\nInmate_id · Charge · Agency]
    C --> D{Hold\nStatus?}
    D -- No Hold --> E[Standard Processing]
    D -- Has Hold --> F[Hold Review\n& Coordination]
    E --> G[Court Scheduling]
    F --> G
    G --> H{Delay\nFlag?}
    H -- No Delay --> I[Court Appearance]
    H -- Delayed --> J[⚠️ Delay Alert\nFlagged for Expedite]
    J --> I
    I --> K{Release\nType}
    K -- Completion --> L[✅ Released]
    K -- Parole --> M[Parole Processing]
    K -- Transfer --> N[Inter-Agency Transfer]
    M --> L
    N --> O([🏛️ Receiving Facility])

    style A fill:#4A90D9,color:#fff
    style L fill:#27AE60,color:#fff
    style J fill:#E74C3C,color:#fff
    style O fill:#8E44AD,color:#fff
```

> **Key:** This pipeline maps the full inmate lifecycle from arrest to release. The Prediction Model (Notebook 1) activates at **Booking & Intake** to estimate release duration. The Risk Classifier (Notebook 3) activates immediately after **Data Entry** to flag high-risk cases. Population Forecasting (Notebook 2) aggregates all active cases to project facility load.
