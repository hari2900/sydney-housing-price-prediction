# 🏠 Sydney Housing Price Prediction and Decision Support System

**SIT720 Machine Learning — Distinction Task (Mini Project)**

A complete end-to-end ML pipeline that predicts Sydney property sale prices across three suburbs — from manual data collection through model development, error analysis, and a deployed prediction app.

---

## 📌 Project Overview

This project simulates a data scientist working for a real estate agency, building a housing price prediction and decision-support tool. Rather than optimising purely for accuracy, the focus is on justified, evidence-based decisions at every stage: data collection, feature engineering, model selection, error analysis, and deployment.

**Suburbs covered:** Mosman · Paddington · Campbelltown
**Dataset size:** 100 manually collected sold properties (32–35 per suburb)
**Final model:** Random Forest Regressor (R² = 0.947 on held-out test data)

---

## 📂 Repository Contents

| File | Description |
|---|---|
| `sydney_housing_data.xlsx` | Collected dataset — 100 sold properties across 3 Sydney suburbs, manually sourced from Domain.com.au |
| `sydney_housing_analysis.ipynb` | Full analysis notebook — EDA, feature engineering, model training & cross-validation, error analysis, ML vs LLM vs Human comparison |
| `app.py` | Streamlit web app for live price predictions |
| `sydney_housing_model.pkl` | Trained Random Forest pipeline (saved via joblib) |
| `model_metadata.pkl` | Suburb/property-type options used by the app |
| `report.pdf` | Full written report covering Parts 1–6 |

---

## 📊 Key Results

| Model | CV RMSE | CV R² | Train–CV Gap |
|---|---|---|---|
| Linear Regression | $909,872 | 0.517 | 0.261 |
| **Random Forest ✅** | **$675,209** | **0.745** | **0.210** |
| Gradient Boosting | $792,649 | 0.639 | 0.358 |

Random Forest was selected as the final model — best cross-validated performance and the most resistant to overfitting on a small (~100 row) dataset. On the held-out test split: **R² = 0.947, RMSE ≈ $354K**.

---

## 🚀 How to Run

**1. Install dependencies**
```bash
pip install streamlit scikit-learn joblib pandas numpy matplotlib
```

**2. Reproduce the analysis**
Open and run `sydney_housing_analysis.ipynb` end-to-end (regenerates all figures and re-trains/saves the model).

**3. Launch the prediction app**
```bash
streamlit run app.py
```
Opens at `http://localhost:8501`

---

## 🖥️ App Preview

The app takes suburb, property type, bedrooms, bathrooms, car spaces, building size, and year built, and returns an instant predicted sale price using the trained model.

*(See `report.pdf` for screenshots)*

---

## ⚠️ Limitations

- Land size and distance-to-CBD/station were not consistently available and are excluded as features
- Dataset only captures *sold* properties (survivorship bias)
- Small sample size (32–35 per suburb) limits generalisability
