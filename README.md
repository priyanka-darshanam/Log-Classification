# Log Classification

## Overview
This project implements a hybrid log classification system that combines multiple approaches to handle diverse log patterns effectively. It ensures flexibility and accuracy in processing structured, complex, and poorly labeled log data.

## Classification Approaches
- **Regex**: Handles simple, predictable log patterns using predefined rules.
- **Sentence Transformer + Logistic Regression**: Manages complex patterns with sufficient labeled data by leveraging embeddings and classification layers.
- **LLMs (Large Language Models)**: Used when labeled data is insufficient, providing a fallback for intricate patterns.

## Architecture
- **training/**: Code for training models using Sentence Transformers and Logistic Regression, including regex-based classification.
- **models/**: Stores trained models such as Sentence Transformer embeddings and the Logistic Regression model.
- **resources/**: Contains test datasets, sample outputs, and additional resources.
- **Root Directory**: Hosts the FastAPI server and core logic.

## Setup Instructions
### Install Dependencies
Ensure Python is installed and run:
```sh
pip install -r requirements.txt
```

### Run the FastAPI Server
Start the server with:
```sh
uvicorn server:app --reload
```
Once running, access the API at:
- [Main Endpoint](http://127.0.0.1:8000/)
- [Swagger Docs](http://127.0.0.1:8000/docs)
- [ReDoc](http://127.0.0.1:8000/redoc)

## Usage
Upload a CSV file containing logs to the FastAPI endpoint. Ensure it has:
- `source`
- `log_message`

The output CSV will include an additional column `target_label`, representing the classified log category.
