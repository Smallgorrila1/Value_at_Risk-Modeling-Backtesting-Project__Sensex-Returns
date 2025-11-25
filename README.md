# Value-at-Risk (VaR) Modeling & Backtesting Project

A complete multi-model Value-at-Risk (VaR) framework implemented using real **Sensex daily returns**, following industry-standard market risk methodologies .

---

## 📌 Project Objective

This project estimates and validates downside market risk using:

- Historical Simulation VaR  
- EWMA Volatility-Adjusted VaR (λ = 0.94)  
- Parametric Normal/Geometric VaR  
- EVT–POT (Generalized Pareto Distribution for tail losses)

Training data: **2023 Sensex daily returns**  
Backtesting data: **2024 Sensex daily returns**

**Goals:**

- Compare VaR estimates at 95% and 99%  
- Analyze left-tail and extreme-loss behaviour  
- Perform Kupiec, Independence, and Conditional Coverage backtests  
- Identify the most reliable VaR model under real market conditions  

---

## 📂 Repository Structure
.
├── data/ # Raw & processed data (Excel files)
├── src/ # All model & threshold selection code
├── outputs/ # Plots & exported VaR / EVT outputs
├── reports/ # PDF/Docx full project report
├── README.md # Project documentation
└── requirements.txt # Python dependencies

---

## 🔧 Methodology Overview

### **1. Historical VaR**
Non-parametric percentile of historical returns.

### **2. EWMA Volatility-Adjusted VaR**
Uses λ = 0.94 to scale returns based on current volatility.

### **3. Parametric VaR**
Assumes normally distributed geometric returns.

### **4. EVT–POT VaR**
Models tail behaviour using the Generalized Pareto Distribution (GPD).  
Threshold chosen using Mean Residual Life (MRL) and parameter stability plots via `threshold_selection.py`.

---

## 📉 Backtesting Framework

Each model is validated using **2024 out-of-sample returns**:

- Exception count  
- Failure rate  
- Kupiec Test (LR_uc)  
- Independence Test (LR_ind)  
- Conditional Coverage (LR_cc)

Backtesting summaries exported to Excel in `/data/`.

---

## 📊 Results

Included outputs:

- `VaR_Results_2023.xlsx` — VaR values for all models  
- `VaR_Backtest_Summary.xlsx` — Backtesting results  
- EVT Threshold Selection Plots  
- Left-tail distribution with VaR overlays  

(See `/outputs/` and `/data/` folders.)

---

## 🚀 How to Run the Project

```bash
pip install -r requirements.txt
python src/main.py
```

