📈 Time Series Forecasting API

🚀 Overview

This API provides time series forecasting using the simple moving average of past 4 weeks' values on the same weekday. It is built using FastAPI and supports containerized deployment via Docker.

🛠 Setup Instructions

1️⃣ Run Locally (Without Docker)

Prerequisites

Python 3.9+

pip installed

Installation

# Clone the repository
git clone <your-repo-url>
cd <your-project-directory>

# Install dependencies
pip install -r requirements.txt



2️⃣ Run with Docker

Build the Docker Image

docker build -t forecasting-api .

Run the Container

docker run -p 8000:8000 forecasting-api

🔥 API Usage

Endpoint

POST /forecasting

Accepts JSON payload containing:

historical: A dictionary of past date-value pairs.

start_date: The first date for the forecast.

horizon: Number of future days to predict.

Example Request

{
  "historical": {
      "2024-04-01": 10,
      "2024-04-02": 11,
      "2024-04-03": 14,
      "2024-04-04": 8,
      "2024-04-05": 15,
      "2024-04-06": 6,
      "2024-04-07": 11,
      "2024-04-08": 8,
      "2024-04-09": 3,
      "2024-04-10": 11,
      "2024-04-11": 9,
      "2024-04-12": 6,
      "2024-04-13": 19,
      "2024-04-14": 21,
      "2024-04-15": 6,
      "2024-04-16": 2,
      "2024-04-17": 9,
      "2024-04-18": 7,
      "2024-04-19": 8,
      "2024-04-20": 4,
      "2024-04-21": 20,
      "2024-04-22": 13,
      "2024-04-23": 1,
      "2024-04-24": 10,
      "2024-04-25": 8,
      "2024-04-26": 15,
      "2024-04-27": 14,
      "2024-04-28": 9,
      "2024-04-29": 12,
      "2024-04-30": 3
  },
  "start_date": "2024-05-10",
  "horizon": 7
}

cURL Command

curl -X POST "http://127.0.0.1:8000/forecasting" \
     -H "Content-Type: application/json" \
     -d '{
          "historical": {
              "2024-04-01": 10,
              "2024-04-02": 11,
              "2024-04-03": 14,
              "2024-04-04": 8,
              "2024-04-05": 15,
              "2024-04-06": 6,
              "2024-04-07": 11,
              "2024-04-08": 8,
              "2024-04-09": 3,
              "2024-04-10": 11,
              "2024-04-11": 9,
              "2024-04-12": 6,
              "2024-04-13": 19,
              "2024-04-14": 21,
              "2024-04-15": 6,
              "2024-04-16": 2,
              "2024-04-17": 9,
              "2024-04-18": 7,
              "2024-04-19": 8,
              "2024-04-20": 4,
              "2024-04-21": 20,
              "2024-04-22": 13,
              "2024-04-23": 1,
              "2024-04-24": 10,
              "2024-04-25": 8,
              "2024-04-26": 15,
              "2024-04-27": 14,
              "2024-04-28": 9,
              "2024-04-29": 12,
              "2024-04-30": 3
          },
          "start_date": "2024-05-10",
          "horizon": 7
     }'


Example Response

{"forecast":{"2024-05-10":9.666666666666666,"2024-05-11":12.333333333333334,"2024-05-12":16.666666666666668,"2024-05-13":10.333333333333334,"2024-05-14":2.0,"2024-05-15":9.5,"2024-05-16":7.5}}



🛠 Troubleshooting

If you get an error on docker build, ensure you have Docker installed and running.

If curl returns an error, try accessing http://localhost:8000/docs to check API functionality.

📌 Next Steps

Add support for more advanced forecasting models (Prophet, LSTM, ARIMA, etc.).

Implement input validation for better error handling.

🚀 Now you're all set to forecast time series data! 🚀

