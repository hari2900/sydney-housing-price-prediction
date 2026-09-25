# Sydney Housing Price Prediction and Decision Support System

Distinction ML Mini Project — SIT720

## Contents
- `sydney_housing_data.xlsx` — collected dataset (100 sold properties, 3 Sydney suburbs)
- `sydney_housing_analysis.ipynb` — full analysis notebook (EDA, feature engineering, model training/evaluation, error analysis, ML/LLM/human comparison)
- `app.py` — Streamlit deployment app
- `sydney_housing_model.pkl`, `model_metadata.pkl` — trained model files used by the app

## How to run
1. `pip install streamlit scikit-learn joblib pandas numpy matplotlib`
2. Run the notebook end-to-end to reproduce results and regenerate the model files
3. `streamlit run app.py` to launch the prediction app
