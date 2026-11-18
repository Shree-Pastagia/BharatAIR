# BharatAIR — National Air Quality Data Analysis & Forecasting

<p align="center">
  <img src="logo.png" width="160" alt="BharatAIR Logo" />
</p>

> **Empirical Data Science, Diurnal Analysis & Multi-Horizon Forecasting across 7 Indian Megacities**  
> Built on Central Pollution Control Board (CPCB) continuous ambient air quality monitoring (CAAQMS) telemetry.

---

## 📌 Project Overview

**BharatAIR** is an end-to-end air quality data analysis and forecasting project designed to understand urban particulate pollution ($\text{PM}_{2.5}$) dynamics in India. The project performs comprehensive exploratory data analysis (diurnal inversion, seasonal cycles, meteorological correlations) and evaluates four targeted predictive modeling techniques:

1. **Linear Regression (LR)** — Interpretable parametric baseline capturing linear autocorrelation and trend persistence.
2. **Random Forest (RF)** — Non-parametric ensemble resolving non-linear local threshold effects and short-term volatility.
3. **XGBoost** — Gradient-boosted decision trees optimizing loss gradients on sequential lag features.
4. **Temporal Convolutional Network (TCN)** — Dilated causal sequence modeling for capturing extended multi-day seasonal rhythms.

---

## 📊 Megacities Analyzed

The platform analyzes continuous monitoring networks across **7 Indian megacities**:
* **Delhi** (37 regulatory stations)
* **Bengaluru** (11 regulatory stations)
* **Mumbai** (29 regulatory stations)
* **Hyderabad** (10 regulatory stations)
* **Chennai** (6 regulatory stations)
* **Kolkata** (7 regulatory stations)
* **Ahmedabad** (7 regulatory stations)

---

## 🔍 Key Data Discoveries

1. **The Diurnal Solar Dip & Nighttime Inversion**:
   * Particulate matter ($\text{PM}_{2.5}$) drops during afternoon hours (2:00 PM – 4:00 PM) due to solar boundary layer expansion and vertical thermal dispersion.
   * Particulate matter sharply rises in late evening (8:00 PM – 11:00 PM) as nocturnal radiation cooling compresses the planetary boundary layer, trapping vehicular and industrial emissions.

2. **Model Behavior by Forecast Horizon**:
   * **Near-Term (+1 Hour)**: Tree-based ensemble (**Random Forest** & **XGBoost**) and **Linear Regression** provide exceptional real-time accuracy ($\pm 3.5\text{ to }7.2\text{ }\mu\text{g/m}^3$ MAE) by leveraging immediate lag autocorrelation ($L=24\text{h}$).
   * **Multi-Step (+6 to +24 Hours)**: Sequential architectures (**TCN**) better preserve diurnal phase patterns over longer horizons ($L=168\text{h}$).

---

## 📁 Repository Structure

```
BharatAIR/
├── data/
│   ├── processed/                     # Cleaned, standardized hourly timeseries datasets
│   ├── phase4_audit/                  # Station coverage indices and historical summaries
│   └── telemetry/                     # Continuous rolling live telemetry
├── models/                            # Trained baseline & ML models (LR, RF, XGBoost, TCN)
├── reports/                           # Comprehensive evaluation and statistical reports
├── scripts/                           # Data pipelines & automated CPCB telemetry poller
├── src/bharatair/                     # Core analytical modules (features, baselines, evaluation)
├── web/                               # Interactive React + Vite web dashboard
├── app.py                             # Python presentation dashboard
└── requirements.txt                   # Project dependencies
```

---

## 🚀 Quickstart

### 1. Python Analysis & Dashboards
```bash
# Clone the repository
git clone https://github.com/Shree-Pastagia/BharatAIR.git
cd BharatAIR

# Install dependencies
pip install -r requirements.txt

# Launch interactive Python dashboard
python -m streamlit run app.py
```

### 2. Interactive Web Dashboard
```bash
cd web
npm install
npm run dev
```

---

## 📜 Authorship & License
* **Lead Researcher / Developer**: Shree Pastagia
* **License**: MIT
