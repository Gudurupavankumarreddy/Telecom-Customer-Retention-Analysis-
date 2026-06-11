# Telecom Customer Retention Analysis & Risk Scoring
### End-to-End Data Analyst Portfolio Project

This project focuses on a major revenue challenge for telecom companies: **customer churn** (losing subscribers). By analyzing the behavior of 7,043 customers, this project uncovers why customers leave, calculates the financial impact of their departure, and builds a system to spot high-risk customers before they cancel their service. 

To make these insights actionable, the project includes an interactive web application designed for retention teams to test risk scores and implement saving strategies.

---

## 🎯 Project Objectives
* **Identify Attrition Triggers:** Pinpoint exactly which contract types, billing methods, and service types cause customers to leave.
* **Measure Financial Impact:** Translate percentage-based churn rates into real annual losses and evaluate the return on investment (ROI) of proactive retention campaigns.
* **Build a Risk Scoring Engine:** Assign a clear risk score (from 0 to 100) to every customer, enabling customer service teams to prioritize high-value, high-risk accounts.
* **Deploy a Visual Tool:** Create a user-friendly Streamlit web application so business teams can interact with the data and predictive model seamlessly.

---

## 🛠️ The Tech Stack
* **Data Processing & Analytics:** Python, Pandas, NumPy
* **Data Visualization:** Matplotlib, Seaborn, Plotly Express
* **Predictive Modeling:** Scikit-Learn (Random Forest), XGBoost, SHAP (Model Explainability)
* **Application Deployment:** Streamlit

---

## 📈 Key Business Insights

### 1. The Financial Reality
* Total analyzed customer base: **7,043 subscribers**
* Current churn rate: **26.5%**
* Total annual financial impact: **Over $2.1M** in combined lost yearly revenue and wasted customer acquisition costs (CAC).

### 2. The "High-Risk" Customer Profile
The data revealed a highly vulnerable group of subscribers: **Customers on Month-to-month contracts, who have been with the company for less than a year, and whose monthly bills are above average.**
* This specific group has a staggering **70.5% churn rate**.
* **The Onboarding Window:** The first 6 months are critical. New customers experience a **52.9% churn rate**. If a customer crosses the 24-month mark, their likelihood of leaving drops drastically.

### 3. Key Behavioral Triggers
* **Contracts Matter:** Month-to-month customers are **3.8 times more likely to churn** than customers on annual contracts.
* **Payment Methods:** Customers paying via electronic check churn at a much higher rate than those enrolled in automatic billing (credit card or bank transfer).
* **Support Infrastructure:** Subscribers who do not have technical support bundled into their plans leave at noticeably higher rates.

---

## 🤖 Predictive Model Performance

To find the best balance between spotting actual churners and avoiding false alarms, multiple predictive models were tested. A **Random Forest Classifier** was selected for production because it delivered the most reliable, balanced performance.

* **Overall Accuracy (79.1%):** The system correctly identifies the outcome for nearly 8 out of 10 customers.
* **Precision (61.2%):** When the model flags a customer as "High Risk", they are right over 60% of the time.
* **Recall (55.1%):** The model successfully catches a strong majority of the people who are planning to leave.


TOP CHURN RISK FACTORS:

1. Month-to-Month Contract Type

2. Low Customer Tenure (Short relationships)

3. High Monthly Charges

4. Fiber Optic Internet (Higher price points)

5. Missing Tech Support Add-on

---

## 💡 Strategic Business Recommendations

Based on the data, the business should deploy four targeted initiatives to save at-risk revenue:

1. **Contract Upgrades:** Proactively target month-to-month customers between months 3 and 6 of their lifecycle. Offer a 15% discount if they upgrade to an annual plan.
2. **Auto-Pay Incentives:** Launch a campaign offering a one-time $25 bill credit to electronic check users who switch to automatic payments.
3. **90-Day New Customer Onboarding:** Introduce mandatory check-ins at days 30, 60, and 90 for high-value subscribers to resolve early service issues.
4. **Fiber Optic Support Bundles:** Free up high-value revenue by automatically bundling 6 months of free technical support with all new premium fiber plans.

---

## 🚀 Folder Structure & Setup

### Repository Layout
```files
├── data/
│   └── telco_churn.csv            # Raw customer records
├── output/
│   ├── clean_telco.csv            # Cleaned data ready for tools like Power BI/SQL
│   ├── risk_scoring_model.joblib  # Saved predictive model file
│   ├── executive_recommendations.txt
│   └── *.png                      # Saved analytical charts and performance plots
├── analysis.py                    # Main script for data cleaning, analysis, and ML training
├── app.py                         # Interactive Streamlit Web Application
├── .gitignore                     # Prevents system clutter in the repository
└── requirements.txt               # Required Python packages


💻 How to Run Locally
Clone the repository:

Bash
   git clone [https://github.com/YOUR_USERNAME/telecom-customer-retention.git](https://github.com/YOUR_USERNAME/telecom-customer-retention.git)
   cd telecom-customer-retention


 1. Set up a virtual environment and install packages:

Bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows use: .venv\Scripts\activate
   pip install -r requirements.txt


 2.  Run the data analysis and model training script:
(Note: Double check that the data folder path inside analysis.py matches your local computer path before running).

Bash
   python analysis.py

 3.  Launch the interactive dashboard:

Bash
   streamlit run app.py

👤 Author
Pavan Kumar Reddy

Data Analyst Portfolio Series


