# UIDAI-Hackathon-ASSI-MH

# UIDAI Aadhaar Service Stress Index (ASSI) + Early Warning Risk Prediction System  
### Maharashtra Pilot (Scalable Nationwide) — UIDAI Data Hackathon 2026

This project builds a **district-wise stress monitoring and early-warning system** for Aadhaar enrolment and update services using UIDAI datasets.

It introduces a novel monitoring index called **ASSI (Aadhaar Service Stress Index)** and combines it with:
- **Red-zone entry alert system**
- **Next-month overload risk prediction (probability-based)**
- **Rolling forecast validation**
- **Policy simulation module** to estimate impact of interventions

✅ Designed as a **Maharashtra pilot** and fully scalable for **India-wide deployment**.

---

## 🚀 Key Features
✅ **ASSI Stress Index (0–100)**: single score measuring service stress per district/month  
✅ **Stress Category Zones**: Stable / Watchlist / Critical  
✅ **Red Zone Entry Alerts**: detects districts newly entering critical stress  
✅ **Risk Prediction Model**: predicts next-month overload risk probability  
✅ **Rolling Forecast Validation**: ensures reliability over time  
✅ **Root Cause Explainability**: feature importance analysis  
✅ **Policy Simulation**: estimates stress/risk reduction after interventions  
✅ **Auto Chart Saving**: important charts saved for report in `REPORT_CHARTS/`

---

## 📌 Problem Statement
Aadhaar service centers may experience overload due to sudden spikes in enrolment and update demand.
This can lead to delays, operational failures, and poor citizen service outcomes.

**Goal:**  
Predict potential overload risks in advance and recommend actions to reduce stress before failures occur.

---

## 📂 Datasets Used (UIDAI)
This project uses UIDAI-provided datasets:
1. **Aadhaar Monthly Enrolment Data**
2. **Aadhaar Demographic Monthly Update Data**
3. **Aadhaar Biometric Monthly Update Data**

> Due to portal download constraints, this implementation is based on **Maharashtra** datasets as a pilot.

---

## 🧠 Methodology (High Level)
1) Data cleaning + preprocessing (month extraction, district cleaning)  
2) Merge datasets → master district-month dataset  
3) Feature engineering (velocity, churn, load density etc.)  
4) Compute **ASSI** using normalized weighted factors  
5) Create stress zones + red-zone alert events  
6) Train ML model using dynamic threshold labels  
7) Generate next-month risk probabilities  
8) Rolling forecast validation across last 6 months  
9) Policy simulation: stress & risk reduction analysis

---

## 📊 Output Visualisations
Key saved charts are available in:

📁 `report/selected_charts/`  

Includes:
- Activity trends
- Top districts by demand
- ASSI trend & heatmap
- Alerts table
- Risk probability ranking
- Rolling validation
- Policy impact dashboards

---

## 🏗 Repo Structure
UIDAI-Hackathon-ASSI-MH/
│
├── notebook/
│   └── UIDAI_Data_Hackathon_FINAL.ipynb
│
├── report/
│   ├── UIDAI_Hackathon_Report.pdf
│   └── figures/
│       ├── EDA_Activity_Trend.png
│       ├── EDA_Top20_District_Enrolment.png
│       ├── EDA_Heatmap_Enrolment_District_Month.png
│       ├── ASSI_Mean_Trend.png
│       ├── ASSI_Stress_Zones_Donut.png
│       ├── ASSI_Heatmap_District_Month.png
│       ├── ALERT_RedZone_Entries_Table.png
│       ├── 0RISK_Top20_Probability.png
│       ├── RISK_Probability_Distribution.png
│       ├── MODEL_Rolling_Metrics.png
│       ├── EXPLAIN_Feature_Importance.png
│       ├── POLICY_Stress_Reduction_Top20.png
│       ├── POLICY_ASSI_Heatmap_BEFORE.png
│       ├── POLICY_ASSI_Heatmap_AFTER.png
│       └── POLICY_Recommendation_Table.png
│
├── data/
│   ├── Aadhaar_Biometric_Monthly_Update_Maharashtra.csv
│   ├── Aadhaar_Demographic_Monthly_Update_Maharashtra.csv
│   ├── Aadhaar_Monthly_Enrolment_Maharashtra.csv
│
├── outputs/
│   ├── MH_final_ASSI_full.csv
│   ├── MH_risk_predictions_full.csv
│   ├── MH_simulated_ASSI_full.csv
│   ├── MH_policy_impact_full.csv
│   └── MH_policy_impact_top20.csv
│
├── requirements.txt
├── README.md
└── LICENSE 
