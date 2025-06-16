
# 🌦️ Weather ETL Pipeline using GCP & BigQuery

This project is a real-time ETL (Extract, Transform, Load) pipeline that fetches current weather data from the OpenWeather API and loads it into Google BigQuery using Cloud Functions.

## 🔧 Tech Stack
- **Google Cloud Functions (1st Gen)**
- **BigQuery**
- **OpenWeatherMap API**
- **Python 3.10**
- **Requests & Google Cloud Libraries**

## 🚀 Features
- Real-time weather data ingestion
- Data transformation to BigQuery-compatible schema
- Serverless, event-driven design using HTTP-triggered Cloud Function
- Modular structure for easy updates

## 📁 Project Structure
weather-etl/
├── main.py # Cloud function with weather ETL logic
├── config.py # Config file with API keys and project IDs
├── requirements.txt # Python dependencies
└── README.md # Project documentation


## ⚙️ Setup & Deployment

1. Replace `config.py` with your actual values:
```python
PROJECT_ID = "your-gcp-project-id"
DATASET_ID = "your_dataset"
TABLE_ID = "your_table"
API_KEY = "your_openweather_api_key"
CITY = "your_city"
Deploy to Google Cloud Functions:


gcloud functions deploy weather_fetch \
  --runtime python310 \
  --trigger-http \
  --allow-unauthenticated \
  --entry-point fetch_weather_data \
  --source . \
  --region us-central1 \
  --no-gen2
Trigger the function by visiting the provided HTTPS URL.

🧪 Sample Output
Weather data inserted successfully!
📊 Sample Record in BigQuery

{
  "timestamp": "2025-06-16T12:10:00Z",
  "city": "Pune",
  "temp": 30.5,
  "humidity": 75,
  "weather": "Clouds"
}
📌 Future Enhancements
Add support for batch ingestion across multiple cities

Schedule Cloud Function with Cloud Scheduler

Add a dashboard in Streamlit or Looker

Author: Aman Kanthiwar
