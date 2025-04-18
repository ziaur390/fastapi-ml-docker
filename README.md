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

The expected response is:

```json
{"prediction": 1, "probability": 0.965}
```

You can also access the interactive documentation of the API at `http://localhost:8000/docs` or `http://localhost:8000/redoc`.

## Contributing

If you have a Data Science mini-project that you'd like to share, please follow the guidelines in [CONTRIBUTING.md](https://github.com/Praveen76/Data-Science-Mini-Projects/blob/main/contributing.md).

## Code of Conduct
Please adhere to our [Code of Conduct](https://github.com/Praveen76/Data-Science-Mini-Projects/blob/main/CODE_OF_CONDUCT.md) in all your interactions with the project.

## License

This project is licensed under the [MIT License](LICENSE).

## Contact

For questions or inquiries, feel free to contact me on [Linkedin](https://www.linkedin.com/in/praveen-kumar-anwla-49169266/).

## **About Me**:
I’m a seasoned Data Scientist and founder of [TowardsMachineLearning.Org](https://towardsmachinelearning.org/). I've worked on various Machine Learning, NLP, and cutting-edge deep learning frameworks to solve numerous business problems.
