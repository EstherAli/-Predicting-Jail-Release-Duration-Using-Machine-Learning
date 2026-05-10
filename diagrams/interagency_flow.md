# Inter-Agency Coordination Flow

```mermaid
flowchart TD
    LMDC([🏛️ Louisville Metro\nDept of Corrections\nLMDC]) 

    LMDC <-->|Booking Records\nTransfer Requests| SHERIFF[🚔 Jefferson County\nSheriff's Office]
    LMDC <-->|Court Dates\nDetainer Orders| COURTS[⚖️ Jefferson Circuit\nCourt System]
    LMDC <-->|Federal Detainees\nICE Holds| FEDERAL[🦅 Federal Bureau\nof Investigation\nFBI]
    LMDC <-->|Firearms Charges\nCustody Transfers| ATF[🔫 Bureau of Alcohol\nTobacco Firearms\nATF]
    LMDC <-->|Parole Reviews\nSupervision Orders| PAROLE[📋 Kentucky Dept\nof Corrections\nKDOC]
    LMDC <-->|Population Data\nCapacity Reports| STATE[🏢 Kentucky Justice\n& Public Safety\nCabinet]

    ANALYTICS([📊 Predictive Analytics\nSystem]) --> LMDC
    ANALYTICS -.->|Delay Alerts| COURTS
    ANALYTICS -.->|Risk Flags| SHERIFF
    ANALYTICS -.->|Population Forecast| STATE

    style LMDC fill:#2C3E50,color:#fff
    style ANALYTICS fill:#27AE60,color:#fff
    style FEDERAL fill:#2980B9,color:#fff
    style ATF fill:#C0392B,color:#fff
    style COURTS fill:#8E44AD,color:#fff
    style PAROLE fill:#E67E22,color:#fff
    style STATE fill:#16A085,color:#fff
    style SHERIFF fill:#7F8C8D,color:#fff
```

> **Data Flow:** Solid lines represent existing operational data exchanges. Dashed lines represent the **enhanced coordination** enabled by the predictive analytics system — automated alerts for court delays, risk notifications to partner agencies, and population forecasts shared with state oversight bodies.
