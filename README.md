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

🚀 Quick Start – Run Locally
1️⃣ Clone the Repository
```
git clone https://github.com/Dattathreya1/SVARA_REPLY_CLASSIFICATION.git
cd SVARA_REPLY_CLASSIFICATION
```

2️⃣ (Optional but Recommended) Create a Virtual Environment
```
python -m venv venv
# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate
```

3️⃣ Install Dependencies
```
pip install -r requirements.txt
```

4️⃣ Start the FastAPI Server
```
uvicorn app:app --reload --port 8000
```
The API is now live at http://127.0.0.1:8000


Test the API

Interactive Swagger UI
Visit http://127.0.0.1:8000/docs
, click POST /predict, then Try it out and enter:
Example Text
```
{
  "text": "Looks good—schedule a demo"
}
```
Click Execute to receive a JSON prediction.

## Docker
```
docker build -t reply-classifier .
docker run -p 8000:80 reply-classifier
```
