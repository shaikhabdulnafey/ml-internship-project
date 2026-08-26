# E-Commerce Forecasting & API Integration

**Prepared by:** SHAIKH ABDUL NAFEY
**Primary Contribution:** Sales/Demand Forecasting + ML Model/API Integration
**Project:** E-Commerce Customer Analytics & Forecasting
**Dataset:** Public Olist Brazilian E-Commerce Dataset

## 1. Project Overview

This project provides an end-to-end workflow covering:

* Data Engineering
* Customer RFM Analytics
* K-Means Segmentation
* Sales Forecasting
* Model Packaging
* FastAPI Integration
* Streamlit Dashboard

My primary responsibility is the **forecasting and model-serving layer**.

## 2. Sales / Demand Forecasting

The forecasting module:

1. Calculates order-level revenue.
2. Aggregates revenue by purchase date.
3. Adds missing dates as zero-revenue days.
4. Uses the final 30 days as a holdout period.
5. Trains an **Exponential Smoothing** model without trend or seasonality.
6. Evaluates the model using **MAE** and **RMSE**.
7. Refits the model and generates future forecasts.

## 3. Model & API Integration

The project uses the following model artifacts:

```text
models/
├── segmentation_scaler.pkl
├── segmentation_kmeans.pkl
└── sales_forecast.csv
```

The FastAPI service provides:

```text
GET  /health
POST /predict/segment
POST /predict/forecast
GET  /docs
```

The API and dashboard use the model artifacts and forecast outputs for predictions and visualization.

## 4. Local Deployment

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Start the FastAPI service:

```bash
uvicorn api.main:app --host 0.0.0.0 --port 8000
```

Start the Streamlit dashboard:

```bash
streamlit run dashboard/app.py
```

FastAPI documentation will be available at:

```text
http://127.0.0.1:8000/docs
```

## 5. Repository Structure

```text
ecommerce-ml-project/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
├── api/
├── dashboard/
├── models/
├── sample_data/
├── src/
└── docs/
```



## 8. Required Libraries

The project uses the following main Python libraries:

```text
pandas
numpy
scikit-learn
statsmodels
joblib
fastapi
uvicorn
streamlit
```



