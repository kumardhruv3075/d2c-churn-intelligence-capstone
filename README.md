# d2c-churn-intelligence-capstone
A complete end-to-end machine learning system for predicting and preventing customer churn for a D2C personal care brand.A complete Data Science + Machine Learning + FastAPI + Segmentation project built using:Python (Pandas, Scikit-learn, FastAPI, Pydantic), Docker (Containerization), Jupyter Notebook Automated API Testing.
This project analyses real behavioural customer data, covering data auditing, RFM segmentation, predictive modelling, error analysis, and a live REST API deployment.
# Objectives
✔ Audit and merge 7 raw customer datasets
✔ Group customers using RFM (Recency, Frequency, Monetary) segmentation
✔ Build and evaluate a machine learning churn prediction model
✔ Optimise decision thresholds for business cost-efficiency
✔ Deploy a live REST API for real-time customer scoring
✔ Recommend segment-specific retention budget allocations
# Tools Used
Python (Pandas, NumPy)
Machine Learning (Scikit-learn, Joblib)
FastAPI / Uvicorn, Matplotlib / Seaborn
Docker
Jupyter Notebook

# Dataset Source: 
D2C Brand Internal Data.
# Original Input Files: 
customers.csv, orders.csv, support_tickets.csv, web_app_events.csv, campaigns.csv, churn_labels.csv 
# Processed Dataset: 
modeling_snapshot.csv 
Created by merging and feature engineering the above files based on historical data prior to the June 30, 2024 snapshot. All further modelling and segmentation are performed on this dataset.
# Tech Stack
Python 3.11, NumPy, Matplotlib, Seaborn, Scikit-learn (Logistic Regression, Random Forest, Gradient Boosting), FastAPI & Pydantic v2Pytest (17/17 API tests), Docker
# Project Workflow
Data Audit & EDA -- Merged 7 datasets without future data leakage. Analysed missing values, outliers, and churn distribution
RFM Segmentation & Strategy -- Scored Recency, Frequency, and Monetary dimensions. Segmented 3,000 customers into 9 actionable groups (e.g., Champions, At-Risk)
Machine Learning Modelling -- Engineered 30 features (e.g., recency_days, negative_ticket_rate). Trained and evaluated baseline and ensemble models. Selected Gradient Boosting and lowered the threshold to 0.45 to prioritise Recall (91%)
API Deployment -- Wrapped the trained model into a REST API using FastAPI. Built endpoints for single and batch predictions with strict input validation. Containerised the service using Docker
# Key Business Questions Answered
Why is the brand silently losing 74% of its customers?
Which specific customers are going to churn in the next 60 days?
How should the ₹5,00,000 retention budget be allocated across customer segments?
Do heavy discounts actually drive long-term customer loyalty?
# Key Insights
Recency is the strongest predictor of churn; customers inactive for 60+ days churn at over 80%.
Tier matters deeply—Bronze tier customers churn at 76%, while Platinum tier churns at only 15%.
Discount hunters are not loyal; heavy discount users churn more than regular buyers.
Missing a churner is 100x more expensive than over-predicting, validating the decision to lower the model threshold to catch 91% of real churners.
# Dashboards & Visuals
API Interface: Swagger UI interactive docs for live churn scoring
Python Visualisations:
Churn rate by membership tier; Recency distribution by churn status; Discount usage vs churn rate(Refer to the part1-eda/charts/ directory and part4-api/ for interactive docs)
# Repository Structure
Plaintextd2c-customer-churn-intelligence/
│
├── part1-eda/                  # Data Audit & Exploratory Data Analysis
├── part2-rfm/                  # RFM Segmentation & Business Strategy
├── part3-model/                # ML Modelling, Error Analysis, Model Card
├── part4-api/                  # FastAPI App, Tests, Dockerfile
└── README.md
How to Run
Clone the repository. 
Install dependencies: pip install -r requirements.txt. 
Review notebooks in part1-eda, part2-rfm, and part3-model
Start the live prediction API: uvicorn app.main:app --reload --port 8000
Run automated API tests: python tests/test_api.py
Access the interactive API docs at `
