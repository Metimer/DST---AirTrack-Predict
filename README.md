# Project: Real-Time Air Traffic Tracker
![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Streamlit](https://img.shields.io/badge/Streamlit-1.0%2B-red)
![License](https://img.shields.io/badge/License-MIT-green)


## Description
This web application allows real-time tracking of air traffic, prediction of flight delays, and estimation of passenger flows using Machine Learning (ML) models. 
It is designed for developers, aviation enthusiasts, or analysts who want to visualize and analyze air data without a budget.

**Key Features**:

- Real-time flight tracking (positions, altitudes, speeds) via free APIs.
- Delay predictions based on historical and live data (weather, traffic).
- Passenger flow estimation via ML inferences (proxies like flight volume or airport checkpoints).
- Intuitive user interface with Streamlit for interactive dashboards.
- Automated ETL pipeline with Airflow to ingest and process data, stored in Snowflake (use a free/trial account for dev).



The project is open-source and suitable for personal or educational development. It uses free data sources like OpenSky Network, OpenWeatherMap, and datasets from the Bureau of Transportation Statistics (BTS).

## Tech Stack

**Frontend**: Streamlit (for simple and interactive web UI).
**Backend/ETL**: Apache Airflow (task orchestration), PySpark (data processing), Snowflake (cloud storage, with free tier for tests).
**Language**: Python 3.10+.
**ML**: Scikit-learn or TensorFlow for prediction models (e.g., Random Forest for delays, time-series for flows).
**Others**: Requests for APIs, Pandas for data manipulation.

## Prerequisites

- Python 3.10 or higher.
- A free account on Snowflake (for storage).
- Free API keys for data sources (e.g., OpenSky, OpenWeatherMap).
- Airflow installed locally or via Docker for ETL.

## Installation

## 1️⃣ Clone the repository

```bash 
$ git clone https://github.com/your-username/DST---AirTrack-Predict.git
$ cd DST---AirTrack-Predict
```

## 2️⃣ Create a virtual environment

```bash 
$ python -m venv venv
$ source venv/bin/activate  # On Unix/Mac
$ venv\Scripts\activate  # On Windows
``` 

## 3️⃣ Install dependencies

```bash
$ pip install -r requirements.txt
``` 


## Configure environment variables (in a .env file):
```text
OPENWEATHER_API_KEY=your_key       #(free from openweathermap.org)
OPENSKY_USERNAME="your_username" 
OPENSKY_PASSWORD="your_password"     #(free account from opensky-network.org)
SNOWFLAKE_USER="your_user"
SNOWFLAKE_PASSWORD="your_password"
 ``` 


## Launch Airflow for ETL:

```bash 
$ airflow standalone  # Or use Docker Compose if configured
``` 

## Launch the Streamlit app:

```bash 
$ streamlit run app.py
``` 


## Access the app at

```bash 
$ http://localhost:8501
``` 


## Usage

Real-Time Tracking: The app displays an interactive map of flights via OpenSky data.
Predictions: Enter a flight/airport to get delay estimates (based on ML trained on BTS datasets).
ETL: Airflow schedules jobs to pull API data, process with PySpark, and store in Snowflake.

## To train ML models:

Run python train_ml.py with historical datasets (downloadable via links below).

## Data Sources

- **OpenSky Network**: Real-time flight tracking (free). Link incoming
- **OpenWeatherMap**: Weather data for delay predictions (free tier). Link incoming
- **BTS Delay Data**: US historical datasets for ML. Link incoming
- **TSA Checkpoint**: US passenger flows (free). Link incoming
- **Others**: AviationStack (limited free tier), Kaggle datasets for delays. Links incomings

**Note**: Respect free API limits to avoid blocks.

## Contribution - Quick Guide

**Fork the repo.**
- Create a branch: 
```bash 
$ git checkout -b feature/new-feature
```
- Commit changes:
```bash 
$ git commit -m 'Add new feature'
 ```
- Push:
```bash
$ git push origin feature/new-feature
```
Be free to open a Pull Request.

We encourage contributions to improve ML models or add new sources!

**License**

This project is licensed under the MIT License. See the LICENSE file for details.

**Contact**

For questions, open an issue on GitHub or contact us at [metinamerwane@gmail.com]//[ayoub.bouazzaoui@hotmail.com].
