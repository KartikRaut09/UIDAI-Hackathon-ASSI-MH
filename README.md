# UIDAI Data Hackathon 2026 🏛️  
## Aadhaar Service Stress Index (ASSI) + Early Warning Risk Prediction System  
### Maharashtra Pilot (Scalable Nationwide)

![UIDAI Hackathon](https://img.shields.io/badge/UIDAI-Data%20Hackathon%202026-blue)
![Python](https://img.shields.io/badge/Python-3.9%2B-success)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Plotly](https://img.shields.io/badge/Plotly-Interactive%20Charts-purple)
![Scikit Learn](https://img.shields.io/badge/scikit--learn-ML-yellow)

This repository contains a **district-wise stress monitoring + early warning system** for Aadhaar enrolment and update operations using official UIDAI datasets.  
It introduces a novel composite index called **ASSI (Aadhaar Service Stress Index)** and combines it with:

✅ Next-month overload **risk prediction (probability-based ML)**  
✅ **Rolling forecast validation** (last 6 months)  
✅ **Red-zone entry alerts** (districts entering critical stress)  
✅ **Policy simulation** to estimate intervention impact  

> 📌 Built for UIDAI Data Hackathon 2026  
> 📌 Maharashtra pilot due to portal download filtering — fully scalable nationwide

---

## 🔗 Quick Links
- 📄 **Hackathon Report (PDF):** `report/UIDAI_Hackathon_Report.pdf`
- 📓 **Notebook:** `notebook/UIDAI_Data_Hackathon_FINAL.ipynb`
- 📊 **Figures / Charts:** `report/figures/`
- 📁 **Outputs:** `outputs/`

---

## 🎯 Problem Statement
Aadhaar service centers face **uneven and seasonal demand** across districts, leading to:
- Operational overload
- Delays and long queues
- Reduced citizen experience

**Goal:**  
Predict overload risk **before it happens**, identify stress hotspots, and recommend administrative actions (additional counters/staff, schedule optimization, etc.)

---

## ⭐ Key Features
- **ASSI (0–100 Index):** Converts multiple stress drivers into one interpretable score  
- **Stress Zones:** Stable / Watchlist / Critical classification  
- **Early Warning Alerts:** Detect districts newly entering **Critical** zone  
- **Risk Probability Model:** Predicts next-month overload risk per district  
- **Rolling Validation:** Month-by-month evaluation over last 6 months  
- **Explainability:** Feature importance for root cause identification  
- **Policy Simulation:** Estimates expected stress reduction after interventions  

---

## 📂 Datasets Used (UIDAI)
This project uses UIDAI-provided datasets:
1) Aadhaar Monthly Enrolment Data  
2) Aadhaar Demographic Monthly Update Data  
3) Aadhaar Biometric Monthly Update Data  

📌 Current scope: **Maharashtra (Pilot)**  
Due to portal download filtering constraints, this submission is based on Maharashtra datasets. The pipeline supports full India deployment.

---

## 🧠 Methodology (Summary)
1) Load datasets → `date → month` conversion  
2) Aggregate transactions: **District × Month**  
3) Merge enrolment + demographic updates + biometric updates  
4) Feature engineering (stress drivers):
   - Enrolment velocity (spike indicator)
   - Growth acceleration
   - Update churn
   - Load density proxy
   - Total updates / transactions
5) Compute **ASSI** using MinMax scaling + weighted aggregation  
6) Dynamic high-stress labeling: **top 20% ASSI**  
7) Train ML model:
   - GradientBoostingClassifier
   - Balanced sample weights
8) Rolling forecast validation (last 6 months)  
9) Policy simulation & impact dashboards

---

## 📸 Preview of Key Outputs (Charts)

### 1) Activity Trend (Maharashtra)
<img src="reports/figures/EDA_Activity_Trend.png" width="900"/>

### 2) ASSI Stress Trend
<img src="reports/figures/ASSI_Mean_Trend.png" width="900"/>

### 3) Stress Heatmap (District × Month)
<img src="reports/figures/EDA_Heatmap_Enrolment_District_Month.png" width="900"/>

### 4) Next-Month Risk Prediction (Top 20)
<img src="reports/figures/RISK_Top20_Probability.png" width="900"/>

### 5) Rolling Forecast Validation
<img src="reports/figures/MODEL_Rolling_Metrics.png" width="900"/>

### 6) Policy Simulation Impact (Stress Reduction)
<img src="reports/figures/POLICY_Stress_Reduction_Top20.png" width="900"/>


---

## 📁 Repository Structure
```bash
UIDAI-Hackathon-ASSI-MH/
│
├── notebook/
│   └── UIDAI_Data_Hackathon_FINAL.ipynb
│
├── report/
│   ├── UIDAI_Hackathon_Report.pdf
│   └── figures/
│       └── (all report-ready charts as PNG)
│
├── data/
│   ├── Aadhaar_Biometric_Monthly_Update_MH.csv
│   ├── Aadhaar_Demographic_Monthly_Update_MH.csv
│   ├── Aadhaar_Monthly_Enrolment_MH.csv
│   └── README.md
│
├── outputs/
│   ├── MH_final_ASSI_full.csv
│   ├── MH_risk_predictions_full.csv
│   ├── MH_simulated_ASSI_full.csv
│   ├── MH_policy_impact_full.csv
│   └── MH_policy_impact_top20.csv
│
├── requirements.txt
└── README.md
