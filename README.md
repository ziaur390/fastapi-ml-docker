# Dockerize-ML-applications-using-FastAPI

This repository contains code for creating and deploying a machine learning application using FastAPI and Docker. The application is a simple classifier that predicts the survival of passengers on the Titanic based on their features.

## Requirements

- Python 3.8 or higher
- Docker

## Installation

Clone this repository and navigate to the project directory:

```bash
git clone https://github.com/Praveen76/Dockerize-ML-applications-using-FastAPI.git
cd Dockerize-ML-applications-using-FastAPI
```

Build the Docker image:

```bash
docker build -t fastapi-ml-app .
```

Run the Docker container:

```bash
docker run -p 8000:8000 fastapi-ml-app
```

## Usage

The application exposes a REST API that accepts JSON requests and returns JSON responses. The request should contain the following fields:

- `pclass`: Passenger class (1, 2, or 3)
- `sex`: Sex of the passenger (male or female)
- `age`: Age of the passenger (in years)
- `sibsp`: Number of siblings or spouses aboard
- `parch`: Number of parents or children aboard
- `fare`: Ticket fare (in pounds)

The response will contain the following fields:

- `prediction`: The predicted survival of the passenger (0 or 1)
- `probability`: The probability of the prediction (between 0 and 1)

You can use any HTTP client to interact with the API, such as `curl` or `requests`. For example, to make a prediction for a 22-year-old female passenger in the first class with no relatives aboard and a fare of 71 pounds, you can use the following command:

```bash
curl -X POST "http://localhost:8000/predict" -H "Content-Type: application/json" -d '{"pclass": 1, "sex": "female", "age": 22, "sibsp": 0, "parch": 0, "fare": 71}'
```

