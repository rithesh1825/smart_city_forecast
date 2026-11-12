# 🏙️ Smart City Forecast – AI-Powered Urban Prediction System

An AI-powered Smart City Forecasting System developed using Python, Machine Learning, FastAPI, Streamlit, and AWS S3.

This project uses machine learning models to predict important urban parameters, including traffic congestion, electricity demand, waste-bin fill levels, air pollution, and emergency incident probability.

The goal is to demonstrate how machine learning and cloud technologies can support smarter urban planning and resource management.

## 🚀 Project Overview

Modern cities generate large amounts of operational data. Analyzing this data can help city administrators make better decisions about transportation, energy consumption, waste collection, environmental monitoring, and emergency planning.

This project implements a machine learning-based forecasting pipeline with an interactive dashboard and REST API.

Users can enter current city conditions and receive predictions for future urban scenarios.

## ✨ Key Features

### 🚗 1. Traffic Forecasting
- Predicts vehicle count for the next hour.
- Considers current vehicle count, weather, hour, and day of the week.
- Helps demonstrate traffic congestion forecasting.

### 💡 2. Energy Consumption Forecasting
- Predicts electricity grid load 24 hours ahead.
- Uses temperature, current grid load, time, and day information.
- Supports energy demand planning.

### 🗑️ 3. Waste Management Forecasting
- Predicts waste-bin fill levels one day ahead.
- Considers bin type, current fill percentage, and days since collection.
- Helps identify bins that may require collection.

### 💨 4. Air Pollution Forecasting
- Predicts Air Quality Index (AQI) for the next hour.
- Considers current AQI, traffic level, and time.
- Demonstrates environmental monitoring and forecasting.

### 🚨 5. Emergency Risk Prediction
- Estimates the probability of an incident occurring within the next hour.
- Uses weather conditions, traffic level, hour, and day of the week.
- Demonstrates machine learning-based risk estimation.

## 🛠️ Technologies Used

**Programming Language**
- Python

**Machine Learning**
- Scikit-learn
- Random Forest Regressor
- Random Forest Classifier
- Pandas
- NumPy

**Backend Development**
- FastAPI
- Uvicorn
- Pydantic

**Frontend Development**
- Streamlit
- Requests

**Cloud Infrastructure**
- AWS S3
- Boto3

**Data Processing**
- Pandas
- ETL Pipeline
- Synthetic Data Generation
- Joblib Model Serialization

## 🏗️ System Architecture

The project follows a modular machine learning architecture.

1. Data Simulation – Generates sample datasets for five urban domains.
2. Cloud Storage – Stores generated datasets in AWS S3.
3. ETL Processing – Cleans and transforms data into machine learning features.
4. Model Training – Trains Random Forest regression and classification models.
5. Model Storage – Saves trained models and feature information.
6. REST API – Exposes prediction endpoints through FastAPI.
7. Interactive Dashboard – Provides a Streamlit interface for users to submit inputs and view predictions.

## 📂 Project Structure

```text
smart_city_forecast/
│
├── app.py
│   └── FastAPI backend and prediction endpoints
│
├── dashboard.py
│   └── Streamlit interactive dashboard
│
├── simulate.py
│   └── Synthetic urban dataset generation
│
├── etl.py
│   └── Data preprocessing and feature engineering
│
├── train.py
│   └── Machine learning model training
│
├── aws_utils.py
│   └── AWS S3 upload and download utilities
│
├── requirements.txt
│   └── Project dependencies
│
├── data/
│   └── Generated urban datasets
│
└── models/
    └── Trained machine learning models
```

## 🧠 Machine Learning Models

The project uses Random Forest algorithms for different forecasting tasks.

| Prediction Task | Algorithm | Prediction Target |
|---|---|---|
| Traffic | Random Forest Regressor | Vehicle count |
| Energy | Random Forest Regressor | Grid load |
| Waste | Random Forest Regressor | Bin fill percentage |
| Pollution | Random Forest Regressor | AQI |
| Emergency | Random Forest Classifier | Incident probability |

The training pipeline evaluates regression models using Root Mean Squared Error (RMSE) and the classification model using accuracy.

## 📊 Data Generation

The project includes a synthetic data generation module.

The `simulate.py` script generates sample datasets for:

- Traffic conditions
- Energy consumption
- Waste management
- Air pollution
- Emergency incidents

The generated datasets are saved as CSV files and uploaded to AWS S3.

**Note:** These are simulated datasets, not real-time data collected from operational smart cities.

## ⚙️ Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/rithesh1825/smart_city_forecast.git
```

### 2. Navigate to the Project Directory

```bash
cd smart_city_forecast
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Configure AWS Credentials

The project uses AWS S3 for dataset and model storage.

Configure your AWS credentials using the AWS CLI:

```bash
aws configure
```

Provide your AWS access key, secret key, region, and output format.

Ensure the configured AWS account has appropriate permissions for the S3 buckets referenced in `aws_utils.py`.

Never upload AWS credentials or secret keys to GitHub.

### 6. Generate Sample Datasets

```bash
python simulate.py
```

This generates five synthetic datasets and attempts to upload them to the configured S3 data bucket.

### 7. Train Machine Learning Models

```bash
python train.py
```

The training script downloads datasets from S3, performs ETL processing, trains the models, and saves model files and feature information.

The required data must already exist in the configured S3 bucket.

### 8. Start the FastAPI Backend

```bash
uvicorn app:app --reload
```

The API will be available at:

```text
http://127.0.0.1:8000
```

API documentation:

```text
http://127.0.0.1:8000/docs
```

### 9. Start the Streamlit Dashboard

Open another terminal and run:

```bash
streamlit run dashboard.py
```

The interactive dashboard will open in your browser.

Make sure the FastAPI backend is running before submitting predictions.

## 🔗 API Endpoints

| Endpoint | Method | Purpose |
|---|---|---|
| `/` | GET | Check API status |
| `/predict/traffic` | POST | Predict future traffic |
| `/predict/energy` | POST | Predict future energy load |
| `/predict/waste` | POST | Predict waste-bin fill level |
| `/predict/pollution` | POST | Predict future AQI |
| `/predict/emergency` | POST | Estimate incident probability |

Interactive API documentation is available through FastAPI Swagger UI at `/docs`.

## 🎯 Project Objectives

- Apply machine learning to smart city applications.
- Develop forecasting models for urban operations.
- Build REST APIs using FastAPI.
- Create interactive dashboards using Streamlit.
- Implement ETL pipelines for data preprocessing.
- Integrate AWS S3 for cloud-based data and model storage.
- Demonstrate an end-to-end machine learning workflow.

## 🔮 Future Enhancements

- Integrate real-time traffic datasets.
- Connect live weather and pollution APIs.
- Develop geospatial traffic visualization.
- Implement real-time IoT sensor integration.
- Add automated model retraining.
- Deploy the application on AWS.
- Improve prediction performance using advanced machine learning models.

## 👨‍💻 Author

**Rithesh K**

GitHub: https://github.com/rithesh1825

Project Repository:

https://github.com/rithesh1825/smart_city_forecast

## ⚠️ Disclaimer

This project is developed for educational and demonstration purposes.

The forecasting models use simulated datasets and should not be considered validated for real-world city infrastructure decisions or emergency response systems.

---

⭐ If you find this project interesting, please consider giving the repository a star!
