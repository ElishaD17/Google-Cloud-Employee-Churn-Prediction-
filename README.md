# Google Cloud Project: Customer Churn Prediction and Analysis

## Overview
This project utilizes Google Cloud services and other technologies to build a customer churn prediction model and visualize the results through a dashboard. Our goal is to predict customer churn and provide insights through effective data visualization.

## Technologies Used
- **Google BigQuery**: For data storage and query handling.
- **Python**: To connect to the database and perform data manipulation.
- **PyCaret**: An open-source, low-code machine learning library in Python to build the churn prediction model.
- **Google Colab**: To run Python scripts and connect seamlessly to BigQuery.
- **Looker Studio (formerly Google Data Studio)**: To build interactive dashboards for business intelligence.

## Game Plan
1. **Build Database (BigQuery)**
   - Set up a BigQuery instance to store and manage your database.
2. **Connect to Database with Python (Colab to BigQuery)**
   - Use Google Colab to run Python scripts that interact with BigQuery using the BigQuery API.
3. **Build a Churn Model (PyCaret)**
   - Utilize PyCaret in Colab to develop a machine learning model to predict customer churn based on historical data.
4. **Export Data to BigQuery**
   - After model training and predictions, export the results back to BigQuery for further analysis and storage.
5. **Build Dashboard (Looker Studio)**
   - Create interactive dashboards in Looker Studio to visualize and interpret the model’s predictions and performance.

## Setup Instructions
1. **Google Cloud Platform Setup**:
   - Create a new project in Google Cloud.
   - Enable BigQuery API and Looker Studio.
   - Set up authentication by creating service account keys and downloading the JSON key file.
2. **Database Configuration**:
   - Create datasets and tables in BigQuery using the Google Cloud Console or BigQuery UI.
3. **Python Environment Setup**:
   - Open Google Colab and set up the environment by installing necessary libraries using `!pip install google-cloud-bigquery pycaret`.
   - Authenticate using the downloaded JSON key file.
4. **Model Development**:
   - Load and preprocess data from BigQuery.
   - Define and train the churn prediction model using PyCaret.
   - Evaluate the model and export predictions back to BigQuery.
5. **Dashboard Creation**:
   - Connect Looker Studio to the BigQuery datasets.
   - Design and build dashboards using the visual tools provided by Looker Studio.

## Code Snippets
- **Connecting to BigQuery**:
  ```python
  from google.cloud import bigquery
  client = bigquery.Client.from_service_account_json('path_to_service_account.json')
  ```
- **PyCaret Setup for Model Training**:
  ```python
  from pycaret.classification import setup, compare_models
  setup(data = df, target = 'churn_label', session_id=123)
  best_model = compare_models()
  ```
