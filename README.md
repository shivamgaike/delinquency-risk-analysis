# 💳 Credit Delinquency Prediction System
# 📌 Project Overview
This project aims to build a robust, AI-powered predictive system for Geldium to forecast customer credit delinquency. By analyzing historical payment behavior, employment status, and financial leverage (DTI), the system identifies high-risk customers before they default, allowing for proactive intervention.

.

# 📂 Project Structure
├── data/
│   └── Delinquency_prediction_dataset.csv  # Raw data
├── notebooks/
│   └── EDA_and_Cleaning.ipynb             # Exploratory Data Analysis
├── src/
│   ├── model_training.py                  # Random Forest training script
│   └── pipeline.py                        # Automated prediction pipeline
├── reports/
│   ├── EDA_Summary_Report.docx            # Data quality findings
│   └── Business_Summary.pdf               # Strategic recommendations
├── requirements.txt                       # Dependency list
└── README.md                              # Project documentation

# 🔍 Data Insights (EDA)
During the Exploratory Data Analysis phase, several key patterns and anomalies were identified:
1.Missing Values: Significant gaps in Income (~8%) and Loan_Balance (~6%) were handled via Median Imputation.
2.High-Risk Indicators: * Debt-to-Income (DTI): The most significant predictor of default.
  *Employment: Unemployed individuals show a 19.4% delinquency rate.
  *Recent Behavior: Missed payments in the last 90 days (Month_4-6) are stronger predictors than older history.

# 🤖 Modeling & Logic
We utilized a Random Forest Classifier to handle the non-linear relationships found in financial data.
Pipeline Logic:
1.Cleaning: Standardize Employment_Status labels (e.g., merging "EMP" and "Employed").
2.Imputation: Filling numerical gaps with median values to avoid outlier skewing.
3.Encoding: One-Hot Encoding for categorical features like Location and Card_Type.
4.Balancing: Applying balanced class weights to address the 16% minority delinquency class.

Performance Metrics:
1.Primary Metric: Recall (to minimize False Negatives).
2.Secondary Metrics: F1-Score and ROC-AUC ($~0.80+$ target).

# ⚖️ Responsible AI & Fairness
In compliance with financial regulations, the system includes:
  *Explainability: Use of Feature Importance and SHAP values to explain "denials" to stakeholders.
  *Bias Mitigation: Regular testing for Disparate Impact across locations and age groups.
  *Human-in-the-Loop: High-risk interventions (like account freezes) require human review.

# 🚀 Business Impact
  *Delinquency Reduction: Targeted 15% reduction in default rates.
  *Efficiency: Automating 80% of routine payment nudges via agentic AI.
  *Customer Experience: Shifting from reactive "recovery" to proactive financial counseling.


.
# 🛠️Installation & Usage
1.Clone the repository:
git clone https://github.com/yourusername/credit-delinquency-prediction.git\

2.Install dependencies:
pip install -r requirements.txt

3.Run the prediction script:
python src/pipeline.py --input new_customer_data.csv

# 📄 License
Distributed under the MIT License. See LICENSE for more information.
