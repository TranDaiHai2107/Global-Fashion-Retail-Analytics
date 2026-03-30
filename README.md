# Global Fashion Retail Analytics

Sales forecasting and business intelligence system built on the [Global Fashion Retail Stores Dataset](https://www.kaggle.com/datasets/ricgomes/global-fashion-retail-stores-dataset) — 4M+ transactions across 35 stores in 7 countries (US, China, Germany, UK, France, Spain, Portugal).

## Goals

- Compare 9 forecasting models to predict daily retail sales
- Segment customers using clustering on purchase behavior
- Build a BI pipeline with SQL Server (SSIS + SSAS) on a star-schema data warehouse

## Sales Forecasting

All models predict daily total sales converted to USD. Data split: 70/20/10 (train/val/test), evaluated on RMSE, MAE, MAPE.

| Category | Models | Notebooks |
|---|---|---|
| Machine Learning | XGBoost, LightGBM, Random Forest | `XGBoost.ipynb`, `LightGBM.ipynb`, `Random_Forest.ipynb` |
| Statistical | SARIMA, SARIMAX | `SARIMA.ipynb`, `SARIMAX.ipynb` |
| Deep Learning | N-BEATS, NHITS, LSTM, RNN | `NBEATS_GFRS.ipynb`, `NHITS_GFRS.ipynb`, `LSTM.ipynb`, `RNN.ipynb` |

## Customer Segmentation

K-Means and Agglomerative clustering applied on data from the SQL Server data warehouse (`GFRS_DW`). Features: purchase frequency, total spending, category preferences, discount sensitivity.

- `CustomerClustering_Kmeans.ipynb`
- `CustomerClustering_Agglomerative.ipynb`

## BI Layer

- **SSIS** — ETL pipeline: CSV ingestion, currency normalization, loading into star-schema DW
- **SSAS** — OLAP cube with dimensions (Time, Store, Product, Customer, Employee) and measures (Revenue, Quantity, Discount, Transaction Count)
- Documentation: `SSAS and SSIS.pdf`

## Tech Stack

Python (Pandas, NumPy, Scikit-learn, XGBoost, LightGBM, Statsmodels, PyTorch, NeuralForecast), SQL Server, SSIS, SSAS, Power BI, LaTeX

## Setup

```bash
pip install numpy pandas scikit-learn matplotlib seaborn xgboost lightgbm statsmodels torch neuralforecast pyodbc kagglehub
```

Notebooks auto-download data via `kagglehub`. Clustering notebooks require SQL Server with `GFRS_DW` loaded through SSIS.

## Team

| Member | Role |
|---|---|
| Tran Dai Hai | Lead — preprocessing, feature engineering, all ML/DL models, clustering, SSIS, SSAS |
| Mai Nguyen Bao Duy | Forecasting, clustering, SSIS/SSAS, Power BI dashboards |
| Le Nguyen Thanh Cong | Forecasting model development and evaluation |
| Tran Tuyet Nhu | LaTeX documentation and report |
| Le Phuc Thinh | Technical documentation |

## Report

Full analysis: `Sales Analysis and Forecasting over Time Using Machine Learning Models.pdf`
