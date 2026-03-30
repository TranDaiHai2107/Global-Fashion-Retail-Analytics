<div align="center">

# 🌍 Global Fashion Retail Analytics

### Sales Forecasting & Business Intelligence System

[![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![SQL Server](https://img.shields.io/badge/SQL%20Server-2022-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)](https://www.microsoft.com/sql-server)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org)
[![Kaggle Dataset](https://img.shields.io/badge/Kaggle-Dataset-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/datasets/ricgomes/global-fashion-retail-stores-dataset)

*An end-to-end analytics pipeline that combines machine learning forecasting, deep learning time-series models, customer segmentation, and enterprise BI architecture to deliver actionable retail insights across 7 countries.*

---

</div>

## 📑 Table of Contents

- [Overview](#-overview)
- [Dataset](#-dataset)
- [Project Architecture](#-project-architecture)
- [Sales Forecasting Models](#-sales-forecasting-models)
- [Customer Segmentation](#-customer-segmentation)
- [Business Intelligence Layer](#-business-intelligence-layer)
- [Tech Stack](#-tech-stack)
- [Repository Structure](#-repository-structure)
- [Getting Started](#-getting-started)
- [Key Business Insights](#-key-business-insights)
- [Team](#-team)
- [Future Roadmap](#-future-roadmap)

---

## 🔭 Overview

This project builds a **full-stack analytics and forecasting system** on top of the [Global Fashion Retail Stores Dataset](https://www.kaggle.com/datasets/ricgomes/global-fashion-retail-stores-dataset) — simulating a real-world multinational retail environment.

**Core Objectives:**

| Objective | Approach |
|---|---|
| 📈 **Demand Forecasting** | 9 models compared (ML, statistical, deep learning) |
| 👥 **Customer Segmentation** | K-Means & Agglomerative clustering on purchase behavior |
| 🏗️ **Scalable BI Pipeline** | Star-schema data warehouse with SSIS ETL & SSAS OLAP cubes |
| 🌐 **Multi-Market Analysis** | Cross-country, multi-currency retail performance analytics |

---

## 📊 Dataset

> **Source:** [Global Fashion Retail Stores Dataset – Kaggle](https://www.kaggle.com/datasets/ricgomes/global-fashion-retail-stores-dataset)

| Attribute | Details |
|---|---|
| **Records** | 4M+ transactions |
| **Stores** | 35 across 7 countries |
| **Countries** | 🇺🇸 US · 🇨🇳 China · 🇩🇪 Germany · 🇬🇧 UK · 🇫🇷 France · 🇪🇸 Spain · 🇵🇹 Portugal |
| **Currencies** | USD · EUR · CNY · GBP |
| **Features** | Customer demographics, product categories (Feminine / Masculine / Children), pricing, discounts, employee & store metadata |
| **Data Quality** | Intentional noise — missing job titles, inconsistent formats — to simulate real-world challenges |

---

## 🏗 Project Architecture

```
┌──────────────────────────────────────────────────────────────────┐
│                     DATA SOURCE (Kaggle)                        │
│              4M+ transactions · 35 stores · 7 countries         │
└──────────────────────┬───────────────────────────────────────────┘
                       │
          ┌────────────▼────────────┐
          │   DATA ENGINEERING      │
          │  • Python preprocessing │
          │  • SSIS ETL pipeline    │
          │  • SQL Server DW        │
          │  • Star schema design   │
          └─────┬──────────┬────────┘
                │          │
    ┌───────────▼──┐  ┌────▼──────────────┐
    │  ANALYTICS   │  │  BI & REPORTING   │
    │              │  │                   │
    │ • Forecasting│  │ • SSAS OLAP Cube  │
    │   (9 models) │  │ • Power BI        │
    │ • Clustering │  │ • Multi-dimension │
    │   (2 methods)│  │   analysis        │
    └──────┬───────┘  └────────┬──────────┘
           │                   │
           └─────────┬─────────┘
                     ▼
          ┌─────────────────────┐
          │  BUSINESS INSIGHTS  │
          │ Actionable decisions│
          └─────────────────────┘
```

---

## 📈 Sales Forecasting Models

Nine different forecasting approaches were implemented and benchmarked to predict daily sales (converted to USD):

### Machine Learning Models

| Model | Notebook | Description |
|---|---|---|
| **XGBoost** | [`XGBoost.ipynb`](XGBoost.ipynb) | Gradient boosted trees with lag features, calendar features, and rolling statistics |
| **LightGBM** | [`LightGBM.ipynb`](LightGBM.ipynb) | Efficient gradient boosting with early stopping on validation set |
| **Random Forest** | [`Random_Forest.ipynb`](Random_Forest.ipynb) | Ensemble of decision trees for baseline comparison |

### Statistical Models

| Model | Notebook | Description |
|---|---|---|
| **SARIMA** | [`SARIMA.ipynb`](SARIMA.ipynb) | Seasonal ARIMA capturing trend and cyclical patterns |
| **SARIMAX** | [`SARIMAX.ipynb`](SARIMAX.ipynb) | SARIMA with exogenous variables for improved accuracy |

### Deep Learning Models

| Model | Notebook | Description |
|---|---|---|
| **N-BEATS** | [`NBEATS_GFRS.ipynb`](NBEATS_GFRS.ipynb) | Neural Basis Expansion Analysis for interpretable time-series forecasting |
| **NHITS** | [`NHITS_GFRS.ipynb`](NHITS_GFRS.ipynb) | Neural Hierarchical Interpolation for multi-scale temporal patterns |
| **LSTM** | [`LSTM.ipynb`](LSTM.ipynb) | Long Short-Term Memory networks for sequence modeling |
| **RNN** | [`RNN.ipynb`](RNN.ipynb) | Vanilla Recurrent Neural Network with PyTorch |

### Evaluation Strategy

- **Data Split:** 70% Train / 20% Validation / 10% Test (time-ordered)
- **Metrics:** RMSE · MAE · MAPE
- **Validation:** Time-based cross-validation to prevent data leakage
- **Currency Normalization:** All transactions converted to USD using fixed exchange rates

---

## 👥 Customer Segmentation

Two clustering approaches were applied on data extracted from the **SQL Server Data Warehouse (GFRS_DW)**:

| Method | Notebook |
|---|---|
| **K-Means Clustering** | [`CustomerClustering_Kmeans.ipynb`](CustomerClustering_Kmeans.ipynb) |
| **Agglomerative (Hierarchical) Clustering** | [`CustomerClustering_Agglomerative.ipynb`](CustomerClustering_Agglomerative.ipynb) |

**Segmentation Features:**
- Purchase frequency & recency
- Total spending (normalized to USD)
- Product category preferences
- Discount sensitivity

**Applications:** Targeted marketing campaigns, personalized pricing strategies, and customer lifetime value estimation.

---

## 🏢 Business Intelligence Layer

### ETL Pipeline — SSIS

- Extracts raw CSV data from the Kaggle dataset
- Transforms and cleanses records (currency normalization, type casting, deduplication)
- Loads data into a **star-schema data warehouse** on SQL Server

### OLAP Cube — SSAS

- Multidimensional cube built on the data warehouse
- Dimensions: Time · Store · Product · Customer · Employee
- Measures: Revenue · Quantity · Discount Amount · Transaction Count
- Enables drill-down, slice-and-dice analysis

> 📄 Detailed documentation: [`SSAS and SSIS.pdf`](SSAS%20and%20SSIS.pdf)

---

## 🛠 Tech Stack

<table>
<tr>
<td><b>Category</b></td>
<td><b>Technologies</b></td>
</tr>
<tr>
<td>Languages</td>
<td>Python 3.12 · SQL · DAX</td>
</tr>
<tr>
<td>ML / Statistics</td>
<td>Scikit-learn · XGBoost · LightGBM · Statsmodels</td>
</tr>
<tr>
<td>Deep Learning</td>
<td>PyTorch · NeuralForecast (N-BEATS, NHITS)</td>
</tr>
<tr>
<td>Data Processing</td>
<td>Pandas · NumPy · PyODBC</td>
</tr>
<tr>
<td>Visualization</td>
<td>Matplotlib · Seaborn · Power BI</td>
</tr>
<tr>
<td>Database & BI</td>
<td>Microsoft SQL Server · SSIS · SSAS</td>
</tr>
<tr>
<td>Documentation</td>
<td>LaTeX · Jupyter Notebook</td>
</tr>
</table>

---

## 📁 Repository Structure

```
Global-Fashion-Retail-Analytics/
│
├── 📈 Forecasting Models
│   ├── XGBoost.ipynb                # XGBoost regression
│   ├── LightGBM.ipynb               # LightGBM regression
│   ├── Random_Forest.ipynb          # Random Forest regression
│   ├── SARIMA.ipynb                 # Seasonal ARIMA
│   ├── SARIMAX.ipynb                # SARIMA with exogenous variables
│   ├── NBEATS_GFRS.ipynb            # N-BEATS deep learning model
│   ├── NHITS_GFRS.ipynb             # NHITS deep learning model
│   ├── LSTM.ipynb                   # LSTM neural network
│   └── RNN.ipynb                    # RNN neural network
│
├── 👥 Customer Segmentation
│   ├── CustomerClustering_Kmeans.ipynb
│   └── CustomerClustering_Agglomerative.ipynb
│
├── 🏗️ Business Intelligence
│   ├── GFRS_SSAS/                   # SSAS cube project
│   └── GFRS_SSIS.rar                # SSIS ETL package (compressed)
│
├── 📄 Documentation
│   ├── SSAS and SSIS.pdf            # BI architecture report
│   └── Sales Analysis and Forecasting over Time Using Machine Learning Models.pdf
│
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

```bash
# Core dependencies
pip install numpy pandas scikit-learn matplotlib seaborn

# ML models
pip install xgboost lightgbm statsmodels

# Deep learning models
pip install torch neuralforecast

# Database connectivity (for clustering notebooks)
pip install pyodbc

# Dataset
pip install kagglehub
```

### Running the Notebooks

1. **Download the dataset** — Notebooks auto-download via `kagglehub`, or manually from [Kaggle](https://www.kaggle.com/datasets/ricgomes/global-fashion-retail-stores-dataset)
2. **Forecasting** — Open any forecasting notebook and run all cells
3. **Clustering** — Requires a SQL Server instance with the `GFRS_DW` data warehouse loaded via SSIS
4. **BI Layer** — Import the SSIS package and deploy the SSAS cube using Visual Studio / SSDT

---

## 💡 Key Business Insights

- **Cross-country performance comparison** with currency-adjusted revenue
- **Seasonal demand patterns** identified and quantified per market
- **Discount impact analysis** — correlation between promotion depth and sales lift
- **Customer segments** mapped to actionable marketing strategies
- **Store-level benchmarking** for operational efficiency
- **Model comparison** — identifying the best forecasting approach per product category and region

---

## 👨‍💻 Team

| Member | Role | Contributions |
|---|---|---|
| **Trần Đại Hải** | 🎯 Project Lead | Project direction · Data preprocessing & feature engineering · ML/DL model development · Customer clustering · SSIS ETL design · SSAS cube architecture |
| **Mai Nguyễn Bảo Duy** | Developer | Co-developed forecasting & clustering models · SSIS/SSAS implementation · Power BI dashboards |
| **Lê Nguyễn Thành Công** | Developer | Forecasting model development · Model evaluation & benchmarking |
| **Trần Tuyết Như** | Documentation | LaTeX documentation · Final report writing & formatting |
| **Lê Phúc Thịnh** | Documentation | Technical documentation · Result presentation |

---

## 🔮 Future Roadmap

- [ ] Deploy forecasting models as REST API endpoints
- [ ] Build automated model retraining pipeline
- [ ] Integrate real-time exchange rate adjustment
- [ ] Expand segmentation with embedding-based techniques
- [ ] Add interactive web dashboard for model comparison
- [ ] Implement MLflow for experiment tracking

---

<div align="center">

**📄 Full Report:** [`Sales Analysis and Forecasting over Time Using Machine Learning Models.pdf`](Sales%20Analysis%20and%20Forecasting%20over%20Time%20Using%20Machine%20Learning%20Models.pdf)

---

<sub>Built with ❤️ as part of an academic analytics project</sub>

</div>
