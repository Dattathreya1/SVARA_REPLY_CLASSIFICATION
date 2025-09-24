# 📧 Reply Classification API
A machine-learning service that classifies short business replies as **Positive**, **Negative**, or **Neutral**.

This project demonstrates the full pipeline:
* **Data exploration & model training** (Google Colab notebook)
* **Model serving with FastAPI** (`app.py`)
* **Environment management** (`requirements.txt`)
* Optional **Transformer fine-tuning** for greater robustness

Repository mainly includes:
- `app.py`: FastAPI app exposing `/predict`.
- `Dockerfile`: Container configuration.
- `requirements.txt`: Python dependencies.
- `answers.md`:answering few questions
- `SVARA.ipynb`: Notebook for data prep/training.

## Run locally
```
pip install -r requirements.txt
uvicorn app:app --reload --port 8000
```

## Docker
```
docker build -t reply-classifier .
docker run -p 8000:80 reply-classifier
```
