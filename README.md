# Customer Analytics: Segmentation, Churn & Lifetime Value

An end-to-end customer analytics project in three parts: who the customers are, who is likely to leave, and how much they are worth. Each part goes from raw data to concrete marketing recommendations.

Final project for the course AI for Communication & Marketing

## 1️⃣ Part 1: Customer Segmentation
Data audit & cleaning: fixed column names, imputed missing income with the median, removed duplicates, standardised inconsistent categories and handled outliers with IQR and percentiles.

EDA: analysed how income, age, education, marital status and children relate to total spending, and how customers split across purchase channels.

RFM segmentation: scored every customer on Recency, Frequency and Monetary value (quintiles 1–5) and grouped them into 5 segments: Champions, Loyal, New/Promising, At Risk, Lost.

K-Means clustering: chose the number of clusters with the elbow method and silhouette score, then compared the clusters with the RFM segments.

Communication strategy: tailored messages and channels for each segment.

## 2️⃣ Part 2: Churn Prediction
Data cleaning: merged duplicate category labels, imputed missing values (median / mode), removed implausible outliers and encoded categorical variables.
EDA: found an imbalanced target (about 17% churners) and explored churn drivers such as complaints, satisfaction, tenure and days since last order.
Modelling: trained Logistic Regression and Random Forest with class_weight='balanced', evaluated with recall and F1 instead of accuracy because of the imbalance.
Results: Random Forest clearly outperformed Logistic Regression on churners (F1 0.93 vs 0.56).
Insights: feature importance showed tenure, cashback amount and warehouse-to-home distance as the strongest churn drivers, which fed into retention recommendations.

## 3️⃣ Part 3: Customer Lifetime Value (CLV)
Data preparation: merged tables, kept only delivered orders, aggregated instalment payments, used unique customer IDs and removed invalid or extreme order values.
Probabilistic approach: BG/NBD to predict future purchases and Gamma-Gamma to predict average order value, combined into a 90-day CLV.
Machine learning approach: Random Forest regression on RFM and tenure features, compared with the probabilistic model on the same holdout period.
Results: Random Forest achieved lower error (MAE 0.108 vs 0.171).
Marketing recommendations: a win-back campaign for high-value customers at risk, plus a broader CLV-based targeting strategy.

## 🛠️ Tools
Python · pandas · NumPy · scikit-learn · lifetimes · Matplotlib · Seaborn · Jupyter
