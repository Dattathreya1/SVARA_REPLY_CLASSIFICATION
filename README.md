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

Click and open the link in google Colab, before executing all cells make sure
reply_classification_dataset.csv file is uploaded and HARDWARE ACCELERATOR in Change runtime type is set to GPU
```
https://colab.research.google.com/drive/1irGwQXg2HLIG0HZPK3izDFBdY_GZm4zy#scrollTo=NdnUMm76FjdH
```
You can see baseline_tfidf_logreg.pkl file is downloaded.

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
The user interface will looks like:

<img width="1920" height="1022" alt="Screenshot 2025-09-24 191353" src="https://github.com/user-attachments/assets/ecbc04a9-6fa5-4ba1-ab20-98afd0d7ed2c" />

Click on "Post\Predict" and click on "try it out":

<img width="1914" height="1025" alt="Screenshot 2025-09-24 193252" src="https://github.com/user-attachments/assets/025d1ec2-aa94-411c-b7bc-89fdfa9a6caa" />

At the place of string enter some text
EXAMPLE:

```
{
  "text": "Looks good—schedule a demo"
}
```

Click Execute to receive a JSON prediction.

It will show the prediction with accuracy.

<img width="1919" height="1026" alt="Screenshot 2025-09-24 193717" src="https://github.com/user-attachments/assets/de820a69-cfd3-46bc-bc6e-28fc561c4119" />



## Docker
```
docker build -t reply-classifier .
docker run -p 8000:80 reply-classifier
```
