# ETL and Prediction Pipeline for Iris Dataset using Mage AI

## Overview
This project implements an **ETL pipeline** using **Mage AI** to process the **Iris dataset**, train a machine learning model, and make predictions. The pipeline is automated using a **scheduler**.

## Pipeline Structure
The pipeline follows these steps:
1. **Extract Data (`extract_data.py`)**: Loads the Iris dataset into a pandas DataFrame.
2. **Transform Data (`transform_data.py`)**: Applies feature scaling using MinMaxScaler.
3. **Load Data (`load_data.py`)**: Stores the transformed data into an SQLite database.
5. **Make Predictions (`predict.py`)**: Loads the saved model and makes predictions on new data.

## File Structure
```
Task7Qafza/
│── pipelines/
│   ├── etl_prediction_pipeline/
│   │   ├── metadata.yaml
│   │   ├── extract_data.py
│   │   ├── transform_data.py
│   │   ├── load_data.py
│   │   ├── predict.py
│── etl_pipeline.db 
│── my_model.pkl 
```

## Setup & Installation
### 1️⃣ Install Mage AI and Dependencies
```bash
pip install mage-ai pandas scikit-learn sqlite3
```
### 2️⃣ Initialize Mage Project
```bash
mage init Task7Qafza
cd Task7Qafza
```
### 3️⃣ Start Mage Server
```bash
mage start
```
Open **http://localhost:6789** in your browser.


## Scheduling Pipeline Execution
1. Go to **Mage UI** (`http://localhost:6789`)
2. Select `etl_prediction_pipeline`
3. Click `Schedule` and set a desired frequency
4. Save and enable scheduling

## Expected Output
After running the pipeline:
- The **Iris dataset** is extracted and transformed.
- The transformed data is loaded into **`etl_pipeline.db`**.
- The trained model is saved as **`my_model.pkl`**.
- Predictions are made using `predict.py`.
- The pipeline runs automatically based on the set schedule.
