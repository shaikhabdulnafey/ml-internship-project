# ml-internship-project
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
6. Evaluates using **MAE** and **RMSE**.
7. Refits the model and generates future forecasts.

Only approved/public results should be published.

## 3. Model & API Integration

Approved model artifacts may include:

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

The API and dashboard use approved model outputs for predictions and forecasting.

## 4. Local Deployment

```bash
pip install -r requirements.txt
uvicorn api.main:app --host 0.0.0.0 --port 8000
streamlit run dashboard/app.py
```

Local documentation:

```text
http://127.0.0.1:8000/docs
```

Temporary tunnel or private deployment URLs must not be published.

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

## 6. Confidentiality & Security

Do **not** upload:

* Confidential datasets or customer information
* Proprietary source code
* API keys, passwords, or credentials
* Internal architecture or documents
* Confidential screenshots or model results
* Private deployment/tunnel URLs

Use `.env` locally for secrets and exclude it through `.gitignore`.

## 7. GitHub Publication Checklist

* [ ] Only approved/public or sanitized material is included
* [ ] No confidential data or customer information
* [ ] No credentials or private URLs
* [ ] Notebook outputs have been reviewed
* [ ] Model artifacts are approved
* [ ] Dataset licensing/publication status is confirmed
* [ ] Required internship/company approval is obtained

**Final Note:** GitHub documentation does not provide permission to publish confidential information. All code, data, models, screenshots, outputs, and URLs must be reviewed before publication.

## 2. Required Libraries

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

Install all dependencies with:

```bash
pip install -r requirements.txt
```

The `requirements.txt` file should contain the approved versions of the libraries used by the project.
