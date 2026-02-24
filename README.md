# 🌍 Global Fashion Retail Analytics – Forecasting & BI System

## 📌 Project Overview

This project leverages the **Global Fashion Retail Analytics Dataset** to build an end-to-end analytics and forecasting system.

The objective is to:

- Forecast sales performance using advanced time series and machine learning models  
- Segment customers using clustering techniques  
- Design a scalable BI pipeline using SQL Server (SSIS & SSAS)  
- Enable multi-country, multi-currency retail analysis  

This project simulates a real-world multinational retail analytics environment.

---

## 🗂 Dataset Description

The dataset used in this project is the **Global Fashion Retail Stores Dataset** from Kaggle:  
🔗 https://www.kaggle.com/datasets/ricgomes/global-fashion-retail-stores-dataset

It includes:

- 4M+ transaction records  
- 35 stores across 7 countries:
  - United States
  - China
  - Germany
  - United Kingdom
  - France
  - Spain
  - Portugal
- Multi-currency transactions: USD, EUR, CNY, GBP  
- Customer demographics (age, occupation)  
- Product categories (Feminine, Masculine, Children)  
- Pricing & discount data  
- Employee/store performance information  

This dataset introduces controlled complexity such as missing job titles and inconsistent formats to simulate real-world retail data challenges.

---

## 🏗 Project Architecture

### 1️⃣ Data Engineering Layer

- Data cleaning and preprocessing using Python  
- ETL pipeline built with SQL Server Integration Services (SSIS)  
- Data warehouse & cube modeling using SQL Server Analysis Services (SSAS)  
- Star schema design for optimized analytical queries  

---

### 2️⃣ Sales Forecasting Models

Implemented and compared multiple forecasting approaches:

- XGBoost  
- LightGBM  
- SARIMA  
- SARIMAX  
- N-BEATS  
- NHITS  

#### 🔎 Model Selection Strategy

- Time-based cross-validation  
- Evaluation metrics: RMSE, MAE, MAPE  
- Performance comparison across countries and product categories  
- Final model selected based on predictive accuracy and stability  

---

### 3️⃣ Customer Segmentation

Applied clustering techniques to identify customer groups:

- K-Means Clustering  
- Hierarchical Clustering  

#### Segmentation Features

- Purchase frequency  
- Total spending  
- Product category preferences  
- Discount sensitivity  

The clustering results provide insights for targeted marketing and pricing strategies.

---

## 📊 Business Insights Generated

- Cross-country sales performance comparison  
- Currency-adjusted revenue analysis  
- Impact of discount strategies on demand  
- Seasonal demand forecasting  
- Customer segmentation for personalized campaigns  
- Store-level performance benchmarking  

---

## 🧠 Technical Skills Demonstrated

- Time Series Forecasting  
- Machine Learning Model Comparison  
- Deep Learning-based Forecasting (N-BEATS, NHITS)  
- Data Warehousing & OLAP (SSAS)  
- ETL Pipeline Development (SSIS)  
- Clustering & Unsupervised Learning  
- Multi-currency retail analytics  

---

## 🛠 Tech Stack

- Python (Pandas, NumPy, Scikit-learn)  
- XGBoost  
- LightGBM  
- Statsmodels (SARIMA, SARIMAX)  
- Deep Learning Forecasting (NHITS, N-BEATS)  
- Microsoft SQL Server  
- SSIS  
- SSAS  
- Power BI (if applicable)  

---
---

## 👥 Team Contributions

### 🔹 Trần Đại Hải – Project Leader
- Led the overall project development and technical direction  
- Performed data preprocessing and feature engineering  
- Built and optimized Machine Learning forecasting models (XGBoost, LightGBM, SARIMA, SARIMAX, N-BEATS, NHITS)  
- Developed customer clustering models (K-Means, Hierarchical Clustering)  
- Designed and implemented ETL pipelines using SSIS  
- Built OLAP cube and data warehouse architecture using SSAS  

---

### 🔹 Mai Nguyễn Bảo Duy – Team Member
- Co-developed Machine Learning forecasting models  
- Co-developed customer clustering models  
- Implemented SSIS ETL processes  
- Developed SSAS cube structure  
- Built interactive dashboards using Power BI  

---

### 🔹 Lê Nguyễn Thành Công – Team Member
- Contributed to Machine Learning forecasting model development  
- Assisted in model evaluation and performance comparison  

---

### 🔹 Trần Tuyết Như & Lê Phúc Thịnh – Documentation & Reporting
- Developed LaTeX documentation  
- Wrote and formatted the final analytical report  
- Structured technical documentation and result presentation  

---
## 🚀 Future Improvements

- Deploy forecasting models via API  
- Automate retraining pipeline  
- Integrate real-time exchange rate adjustments  
- Expand segmentation using advanced embedding techniques  

---

## 📌 Conclusion

This project demonstrates the ability to build a complete analytical pipeline from raw transactional data to actionable business insights, combining:

- Data Engineering  
- Machine Learning  
- Time Series Forecasting  
- Business Intelligence  

It reflects a real-world multinational retail analytics scenario and showcases end-to-end data analytics capability.
