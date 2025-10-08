# 💳 Bank Transaction Fraud Detection Dashboard (Power BI)

**Author:** Vamsi Krishna Mulinti  
**Tools Used:** Power BI Desktop · DAX · Data Modeling · Geospatial Analytics  

---
### 📂 Download Power BI File
You can view or download the full Power BI dashboard (.pbix) here 👇  
➡️ [Click to Download Fraud Detection Dashboard (.pbix)](https://drive.google.com/uc?export=download&id=1mHpL06hhe7NjQZLQauD9BqUMH827D--H)

## 🎯 Project Objective
To analyze and visualize fraud patterns in banking transactions — identifying risky account types, devices, genders, and geographies to help financial institutions detect and prevent fraud.

---
## 📸 Dashboard Preview
![Fraud Detection Dashboard](Dashboard_FDA.png)


## 🧠 Key Insights
- 💰 **Total Transactions:** 200K+  
- ⚠️ **Total Fraud Cases:** ~10K (≈ 5.04 %)  
- 👤 **Gender Split:** Balanced male vs female fraud ratio.  
- 🏦 **High-Risk Channels:** POS & Mobile App transactions show higher fraud frequency.  
- 🌍 **Fraud Hotspots:** States such as Maharashtra & Bihar show denser clusters of fraud activity.  
- 💵 **Average Account Balance:** ≈ 52.44 K  

---

## 📊 Dashboard Components
1. **KPI Cards:** Total Transactions · Total Fraud Transactions · Fraud Rate (%) · Average Account Balance  
2. **Donut Chart:** Fraud Distribution by Gender  
3. **Stacked Bar Chart:** Fraud Count by Account Type & Device Type  
4. **Gradient Bar Chart:** Transaction Value by State (Colored by Fraud Intensity)  
5. **Map Visual:** Fraud Hotspots by City  
6. **Interactive Slicers:** Account Type · Gender · State · Transaction Type  

---

## 🧮 DAX Measures
```DAX
Total Transactions =
    COUNTROWS('Bank_Transaction_Fraud_Detection')

Fraud Transactions =
    CALCULATE(
        COUNTROWS('Bank_Transaction_Fraud_Detection'),
        'Bank_Transaction_Fraud_Detection'[Is_Fraud] = 1
    )

Fraud Percentage =
    DIVIDE([Fraud Transactions], [Total Transactions], 0)
