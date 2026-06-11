Telecom Customer Churn Prediction & Retention Analytics
End-to-End Data Analytics Project | Python · Machine Learning · Streamlit · Business Strategy

Author: Guduru Pavan Kumar Reddy

🎯 Project Overview
Built a complete churn analytics solution for a telecom provider (7,043 customers) that identifies why customers leave, who is about to leave, and what to do about it — quantified in dollars.

Business Impact: Identified $2.8M+ annual revenue at risk and designed a retention strategy with projected ROI of 400%+.

🛠️ Tech Stack
Layer	Tools
Data & Analysis	Python, Pandas, NumPy
Visualization	Matplotlib, Seaborn, Plotly
Machine Learning	Scikit-learn, XGBoost, SHAP
Deployment	Streamlit (interactive web app)
Model Persistence	Joblib
🔑 What I Did
1️⃣ Data Cleaning & EDA
•
Cleaned 7,043 records, handled missing TotalCharges, fixed data types
•
Computed KPIs: churn rate (26.5%), MRR, CAC loss, lifetime value
2️⃣ Customer Segmentation
•
Contract analysis: Month-to-month churn is 3.8× higher than annual
•
Tenure cohorts: 47% of first-year customers churn (critical window)
•
High-risk profile: Identified 770 customers with 70.5% churn rate
3️⃣ Revenue Impact Modeling
•
Quantified historical loss, MRR loss, and CAC waste
•
Built ROI simulation for retention campaigns (cost vs. saved revenue)
4️⃣ Machine Learning — Risk Scoring System
•
Compared Logistic Regression, Random Forest, XGBoost
•
Built sklearn Pipeline (StandardScaler + OneHotEncoder + Classifier)
•
5-fold cross-validation + SHAP explainability
•
Final model assigns each customer a 0–100 risk score → Low / Medium / High tier
•
Metrics: Accuracy, Precision, Recall, F1, ROC-AUC, Confusion Matrix
5️⃣ Business Recommendations
Translated insights into 5 prioritized initiatives with cost, projected savings, ROI %, and rollout timeline:

•
High-Risk Intervention Campaign
•
90-Day New Customer Onboarding
•
Contract Conversion Incentives
•
Auto-Payment Enrollment Program
•
Fiber Service Optimization
6️⃣ Monitoring Dashboard Design
Designed 3-tier dashboard spec (Executive / Operations / Analytics) with alert thresholds for production monitoring.

7️⃣ Interactive Streamlit App
Deployed a 3-page web app:

•
Dashboard – KPIs & churn visualizations
•
Analysis – Drill-down by service, payment, demographics
•
Predictor – Real-time risk scoring with gauge chart & recommended actions
📁 Project Structure
churn-prediction/
├── data/telco_churn.csv
├── analysis.py              # Full EDA + ML pipeline
├── app.py                   # Streamlit dashboard
├── output/
│   ├── clean_telco.csv
│   ├── risk_scoring_model.joblib
│   ├── customer_risk_scores.csv
│   ├── executive_recommendations.txt
│   └── *.png                # All visualizations
├── requirements.txt
└── README.md
🚀 How to Run
pip install -r requirements.txt
python analysis.py              # runs full pipeline
streamlit run app.py            # launches dashboard
📈 Key Results
Metric	Value
Customers Analyzed	7,043
Churn Rate Identified	26.5%
Annual Revenue at Risk	$2.8M+
Model ROC-AUC	~0.84
High-Risk Tier Precision	70%+
Projected Campaign ROI	400%+
💡 Skills Demonstrated
✅ End-to-end project ownership (data → model → deployment → business strategy) ✅ Statistical analysis & customer segmentation ✅ Supervised ML (classification, model comparison, cross-validation) ✅ Model explainability (SHAP) ✅ Financial modeling (ROI, CLV, revenue impact) ✅ Data storytelling & executive communication ✅ Web app deployment (Streamlit)

📧 Contact: Guduru Pavan Kumar Reddy | Data Analyst Portfolio · 2026
