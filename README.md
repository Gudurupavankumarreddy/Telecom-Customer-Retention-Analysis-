# 📡 Telco Customer Churn Intelligence System

> **Predict which telecom customers are about to leave — and explain why, in plain English.**

A production-ready machine learning system that predicts customer churn with 79%+ accuracy, provides model explanations using SHAP, and generates plain-English AI insights via the Claude API. Built with a clean FastAPI backend and an interactive Streamlit frontend.

---

## 🧩 What Problem Does This Solve?

Telecom companies lose millions every year because customers cancel their plans without warning. This system helps retention teams **identify at-risk customers early** and understand **exactly why** they are likely to leave — so the right action can be taken at the right time.

---

## 🎯 What This Project Does

| Step | What Happens |
|------|-------------|
| **Input** | Enter a customer's demographics, plan type, and billing details |
| **Prediction** | Three ML models (Random Forest, XGBoost, Logistic Regression) predict churn probability |
| **Explanation** | SHAP values reveal which features drove the prediction |
| **AI Insight** | Claude API converts the SHAP data into a plain-English explanation for business users |
| **Output** | Risk level (Low / Medium / High), churn probability %, and actionable retention suggestion |

---

## 🏗️ Project Architecture

```
User Input (Streamlit UI)
        ↓
FastAPI Backend (/predict or /explain)
        ↓
Feature Engineering → ML Pipeline (RF / XGB / Logistic)
        ↓
SHAP Explainer → Top 5 Feature Drivers
        ↓
Claude API → Plain-English Explanation
        ↓
Response: Churn Probability + Risk Level + Explanation
```

### Folder Structure

```
├── app/
│   ├── main.py          # FastAPI routes (/health, /predict, /explain)
│   ├── ml_service.py    # Model loading, feature engineering, SHAP computation
│   ├── llm_service.py   # Claude / OpenAI API integration
│   ├── schemas.py       # Pydantic input/output models with validation
│   └── config.py        # Environment variables, model paths, LLM settings
├── model/
│   ├── pipeline_rf.joblib       # Saved Random Forest pipeline
│   ├── pipeline_xgb.joblib      # Saved XGBoost pipeline
│   ├── pipeline_logistic.joblib # Saved Logistic Regression pipeline
│   └── thresholds.pkl           # Tuned decision thresholds per model
├── streamlit_app.py     # Frontend UI — calls FastAPI, renders results
├── notebook.ipynb       # Full training notebook (EDA → model → save)
├── .env.example         # Template for API keys
└── requirements.txt
```

---

## 🤖 ML Pipeline — How It Was Built

### 1. Data & Feature Engineering
- Dataset: IBM Telco Customer Churn (7,043 rows, 21 features)
- Cleaned `TotalCharges` (coerced non-numeric → 0), mapped `Churn` to 0/1, dropped `customerID`
- **Engineered 2 new features:**
  - `TotalServices` — count of active add-on services per customer
  - `AverageChargeIntensity` — TotalCharges ÷ (tenure + 1), captures spend rate

### 2. Preprocessing
- **Numerical features:** `StandardScaler`
- **Categorical features:** `OneHotEncoder` (drop first, handle unknown)
- Separate preprocessor for Logistic Regression (excludes `TotalCharges` to reduce multicollinearity)
- All steps wrapped in `sklearn.Pipeline` — no data leakage possible

### 3. Train / Validation / Test Split
- 80% train, 20% test (stratified on `Churn`)
- Inner 75/25 split for threshold tuning on a hold-out validation set

### 4. Models & Hyperparameter Tuning
All three models used `class_weight="balanced"` / `scale_pos_weight` to handle class imbalance (~73% No-churn, ~27% Churn).

`GridSearchCV` with 5-fold `StratifiedKFold`, optimizing for **F1-score**:

| Model | Tuned Parameters |
|-------|-----------------|
| Logistic Regression | C, solver |
| Random Forest | n_estimators, max_depth, min_samples_split |
| XGBoost | max_depth, learning_rate, n_estimators, subsample |

### 5. Threshold Tuning
Default threshold (0.5) is suboptimal for imbalanced churn data. For each model, the optimal threshold was found by scanning 101 values (0.01 → 0.99) on the validation set and selecting the one that maximized F1-score.

### 6. Final Results (Test Set)

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|-------|----------|-----------|--------|----------|---------|
| Logistic Regression | ~79% | ~0.62 | ~0.72 | ~0.67 | ~0.84 |
| Random Forest | ~79% | ~0.64 | ~0.63 | ~0.63 | ~0.83 |
| XGBoost | ~79% | ~0.63 | ~0.67 | ~0.65 | ~0.84 |

> Random Forest selected as default (best F1 after threshold tuning).

### 7. SHAP Explainability
- `shap.TreeExplainer` used for RF and XGBoost
- `shap.LinearExplainer` used for Logistic Regression
- Returns top-5 features per prediction with direction (increases / decreases churn risk)
- Key drivers identified: **tenure**, **contract type**, **monthly charges**, **online security**, **internet service**

---

## 🔌 API Endpoints

Run with: `uvicorn app.main:app --reload --port 8000`
Docs at: [http://localhost:8000/docs](http://localhost:8000/docs)

| Method | Endpoint | What It Does |
|--------|----------|-------------|
| GET | `/health` | Check which models are loaded |
| GET | `/models` | List available model options |
| POST | `/predict` | Returns churn probability + SHAP features |
| POST | `/explain` | Same as /predict + plain-English AI explanation |

### Example Request (`/predict`)

```json
POST /predict
{
  "gender": "Male",
  "SeniorCitizen": 0,
  "Partner": "Yes",
  "Dependents": "No",
  "tenure": 5,
  "PhoneService": "Yes",
  "MultipleLines": "No",
  "InternetService": "Fiber optic",
  "OnlineSecurity": "No",
  "OnlineBackup": "No",
  "DeviceProtection": "No",
  "TechSupport": "No",
  "StreamingTV": "Yes",
  "StreamingMovies": "Yes",
  "Contract": "Month-to-month",
  "PaperlessBilling": "Yes",
  "PaymentMethod": "Electronic check",
  "MonthlyCharges": 85.0,
  "TotalCharges": 425.0,
  "model_choice": "rf"
}
```

### Example Response

```json
{
  "churn_probability": 0.7812,
  "churn_prediction": 1,
  "risk_level": "High",
  "model_used": "rf",
  "threshold_used": 0.412,
  "top_shap_features": [
    { "feature": "tenure", "shap_value": -0.3241, "impact": "decreases churn risk" },
    { "feature": "Contract_Month-to-month", "shap_value": 0.2874, "impact": "increases churn risk" },
    { "feature": "MonthlyCharges", "shap_value": 0.1932, "impact": "increases churn risk" },
    { "feature": "OnlineSecurity_No", "shap_value": 0.1543, "impact": "increases churn risk" },
    { "feature": "TotalServices", "shap_value": -0.0921, "impact": "decreases churn risk" }
  ]
}
```

---

## 🤖 LLM Integration (Claude API)

The `/explain` endpoint sends SHAP features + customer facts to Claude and receives a plain-English retention summary:

> *"This customer is at high risk of churning (78% probability). They are on a month-to-month contract with only 5 months of tenure and high monthly charges of $85, which are the key drivers of their risk. Consider offering a discounted one-year contract to improve retention."*

- Provider configurable via `.env` (`anthropic` or `openai`)
- Falls back to a rule-based explanation if no API key is set — so the app works without any LLM key
- Prompt engineered for business users — no SHAP jargon in the output

---

## ⚙️ Setup & Run

### 1. Clone and install

```bash
git clone https://github.com/Gudurupavankumarreddy/telco-churn-intelligence.git
cd telco-churn-intelligence
pip install -r requirements.txt
```

### 2. Configure environment

```bash
cp .env.example .env
# Edit .env and add your ANTHROPIC_API_KEY (optional — app works without it)
```

### 3. Train the models (or use pre-saved)

```bash
# Run notebook.ipynb in Jupyter to generate model files in /model
# Or use the pre-saved .joblib files if already present
```

### 4. Start FastAPI backend

```bash
uvicorn app.main:app --reload --port 8000
```

### 5. Start Streamlit frontend

```bash
streamlit run streamlit_app.py
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| ML Models | Scikit-learn, XGBoost |
| Explainability | SHAP (TreeExplainer, LinearExplainer) |
| API Backend | FastAPI, Pydantic, Uvicorn |
| Frontend | Streamlit |
| LLM Integration | Anthropic Claude API (claude-3-haiku) |
| Data Processing | Pandas, NumPy |
| Model Persistence | Joblib, Pickle |
| Config Management | Python-dotenv |

---

## 📌 Key Design Decisions

**Why a separate FastAPI backend?**
The v1 Streamlit app loaded models directly — fine for demos, but wrong for production. FastAPI separates ML logic from UI, enables multiple frontends, and makes the system testable via HTTP.

**Why threshold tuning?**
A 0.5 default threshold on imbalanced churn data (73/27 split) misses too many churners. Threshold tuning on a hold-out validation set pushed recall significantly higher without destroying precision.

**Why SHAP + LLM together?**
SHAP gives precise, numeric feature attribution. Claude translates that into a sentence a retention manager can act on. Neither alone is sufficient — SHAP is too technical, LLM hallucinations without SHAP grounding are unreliable.

**Why a rule-based LLM fallback?**
So the system is fully functional in environments without API keys. Demos, CI pipelines, and offline usage all work out of the box.

---

## 👤 Author

**Guduru Pavan Kumar Reddy**
B.Tech — Computer Science (AI & ML), Parul University, 2025

[LinkedIn](https://linkedin.com/in/pavankumar0415) · [GitHub](https://github.com/Gudurupavankumarreddy) · [Portfolio](https://pavan-data-portfolio.netlify.app)
