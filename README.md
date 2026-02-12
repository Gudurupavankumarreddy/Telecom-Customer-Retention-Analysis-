# 📡 Telecom Customer Churn Analysis
### End-to-End Data Analytics & Machine Learning Portfolio Project

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--Learn-ML-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-2ea44f?style=for-the-badge)
![Timeline](https://img.shields.io/badge/Completed_In-20_Days_(2_Month_Deadline)-8A2BE2?style=for-the-badge)

</div>

---

## 📌 Repository Name
```
telecom-churn-analysis
```

## 📝 Repository Description
```
End-to-end telecom customer churn prediction | EDA · Customer Segmentation · Revenue Impact Modeling · Random Forest ML Risk Scoring | Python, Pandas, Scikit-learn
```

---

## 🧠 Business Problem

> **Every year, telecom companies lose millions in revenue from customer churn.**
> This project answers three critical questions:
> - **Who** is about to leave?
> - **Why** are they leaving?
> - **What** can we do to retain them — and what's the ROI?

This is a **complete, production-style analytics pipeline** — from raw data to boardroom-ready business recommendations.

---

## 📊 Key Results at a Glance

| Metric | Result |
|---|---|
| 🎯 Model Accuracy | ~80% |
| 📉 Overall Churn Rate | 26.5% |
| 🚨 High-Risk Customers Flagged | 770 customers (70.5% churn rate) |
| 💸 Annual Revenue at Risk | $2.8M+ |
| 📈 Retention Campaign ROI | 500%+ |
| ⚡ Delivered In | **20 days** (vs. 2-month deadline) |

---

## 🗂️ Project Structure

```
telecom-churn-analysis/
│
├── 📁 data/
│   └── telco_churn.csv                    # Source dataset (see link below)
│
├── 📁 output/
│   ├── churn_by_contract_type.png         # Visualization 1
│   ├── churn_by_lifecycle_stage.png       # Visualization 2
│   ├── revenue_impact_analysis.png        # Visualization 3
│   ├── cohort_churn_analysis.png          # Visualization 4
│   ├── risk_scoring_performance.png       # Visualization 5
│   ├── churn_drivers.png                  # Visualization 6
│   ├── customer_risk_scores.csv           # Risk score output per customer
│   ├── risk_scoring_model.joblib          # Saved ML model
│   └── executive_recommendations.txt     # Business summary
│
├── telecom_churn_analysis.ipynb           # 📓 Main analysis notebook
├── requirements.txt                       # Dependencies
└── README.md
```

---

## 🔍 Project Walkthrough

### Section 1 — Data Cleaning & EDA
- Loaded 7,043 customer records
- Fixed data type issues (`TotalCharges` conversion)
- Handled missing values for new customers
- Exported cleaned dataset for further use

### Section 2 — Executive Summary & Key Metrics
- Calculated churn rate, MRR, and total revenue impact
- Identified **$2.8M+ annual revenue loss** from churn
- Benchmarked against industry acquisition cost ($75/customer)

### Section 3 — Customer Segmentation Analysis
- **Contract Type:** Month-to-month customers churn at **42.7%** vs 11.3% for annual contracts — **3.8x higher risk**
- **Tenure Cohorts:** 47.4% of first-year customers churn — the **Critical Risk Window**
- **Service Usage:** Fiber optic (41.9% churn) and customers without Tech Support (41.6% churn)
- **High-Risk Profile:** 770 customers with 70.5% churn rate identified

### Section 4 — Revenue Impact Analysis
- Full financial breakdown: Historical revenue lost, annualized MRR loss, CAC lost
- **Retention Campaign ROI Model:** $15/customer cost → **500%+ projected ROI**

### Section 5 — Cohort Analysis & Churn Timing
- 0–6 month window: **52.9% churn rate** (most critical!)
- Churn drops by 38.9 percentage points after 24 months tenure
- Electronic check users churn at **45%** vs **17%** for auto-pay users

### Section 6 — ML Risk Scoring System
- **Algorithm:** Random Forest Classifier (100 estimators)
- **Pipeline:** StandardScaler + OneHotEncoder via ColumnTransformer
- **19 features** across demographics, services, billing, and contract data
- **Output:** Risk score 0–100 → Low / Medium / High risk tiers

**Model Performance:**

| Metric | Score |
|---|---|
| Accuracy | ~80% |
| Precision | ~65% |
| Recall | ~50% |
| F1-Score | ~0.57 |

### Section 7 — Business Recommendations

| # | Initiative | Est. Cost | Timeline |
|---|---|---|---|
| 1 | High-Risk Customer Intervention | ~$11.5K | Immediate |
| 2 | New Customer Onboarding (90-day) | ~$50K | 1–2 months |
| 3 | Contract Conversion Incentive | Variable | 1 month |
| 4 | Auto-Payment Enrollment Discount | ~$30K | 2–3 weeks |
| 5 | Fiber Optic Service Optimization | ~$30K | 1–2 months |

### Section 8 — Monitoring Dashboard Design
- Executive View (monthly board metrics)
- Operations View (weekly team alerts)
- Analytics View (daily model performance tracking)
- Alert thresholds for risk score spikes, accuracy drift, and segment health

---

## 💡 Top Business Insights

```
🔴  Month-to-month contracts → 3.8x higher churn than annual contracts
🔴  First 6 months = 52.9% churn rate — the most critical retention window
🔴  Electronic check users churn ~2.6x more than auto-pay users
🟡  Fiber optic customers churn at premium rates — price sensitivity issue
🟢  Tech Support subscription reduces churn significantly
🟢  Every $1 spent on the retention campaign returns $5+ in saved revenue
```

---

## 🛠️ Tech Stack

```python
# Data Manipulation
pandas, numpy

# Visualization
matplotlib, seaborn

# Machine Learning
scikit-learn
  ├── RandomForestClassifier
  ├── Pipeline & ColumnTransformer
  ├── StandardScaler, OneHotEncoder
  └── classification_report, confusion_matrix

# Model Persistence
joblib
```

---

## 🚀 How to Run This Project

**Step 1 — Clone the repository**
```bash
git clone https://github.com/YOUR_USERNAME/telecom-churn-analysis.git
cd telecom-churn-analysis
```

**Step 2 — Install dependencies**
```bash
pip install -r requirements.txt
```

**Step 3 — Download the dataset**

📥 Dataset: [Telco Customer Churn — Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

Place the downloaded file at: `data/telco_churn.csv`

**Step 4 — Run the notebook**
```bash
jupyter notebook telecom_churn_analysis.ipynb
```

> Run all cells top to bottom: **Kernel → Restart & Run All**

---

## 📦 Requirements

```
pandas>=1.5.0
numpy>=1.23.0
matplotlib>=3.6.0
seaborn>=0.12.0
scikit-learn>=1.1.0
joblib>=1.2.0
jupyter>=1.0.0
```

---

## 📈 Visualizations

> All charts are saved automatically in the `/output` folder after running the notebook.

| Chart | Description |
|---|---|
| `churn_by_contract_type.png` | Churn rate & revenue loss by contract type |
| `churn_by_lifecycle_stage.png` | Churn risk across customer lifecycle |
| `revenue_impact_analysis.png` | Full financial impact dashboard (4 charts) |
| `cohort_churn_analysis.png` | Churn rate by tenure cohort |
| `risk_scoring_performance.png` | ML model performance & risk tiers |
| `churn_drivers.png` | Top 20 features influencing churn |

---

## 🏢 About This Project

This project was built during a **Data Analytics Internship at Cedura** (Dec 2025 – Feb 2026).

I was given a real telecom dataset and tasked with delivering an end-to-end churn analysis — independently. I completed the full pipeline in **20 days against a 2-month deadline**, covering data cleaning, segmentation, revenue modeling, machine learning, and executive-level recommendations.

**What this demonstrates:**
- ✅ Full data analyst workflow — raw data → business insights
- ✅ Machine learning pipeline: preprocessing, training, evaluation
- ✅ Business storytelling and ROI modeling — not just charts
- ✅ Clean, structured, reproducible code

---

## 👤 Author

**G. Pavan Kumar Reddy**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/pavankumar0415/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Gudurupavankumarreddy)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:gudurupavanpavankumarreddy@gmail.com)

---

<div align="center">

*⭐ If this project helped you, consider giving it a star — it helps others find it too!*

</div>
