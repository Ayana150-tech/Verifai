# VERIFAI — Fake News Detection System

**Group ALGORIX** · Ayana Roy · Shrijeeta Das

An NLP-based web application that classifies news articles and social media posts as **FAKE** or **REAL**, with a confidence score.

---

## Project Structure

```
fake-news-detector/
├── main.py              # FastAPI backend server
├── train.py             # Model training script
├── template/
│   └── index.html       # Frontend web interface
├── model/
│   └── model.pkl        # Trained model (generated after running train.py)
├── requirements.txt
└── README.md
```

---

## How It Works

1. User pastes a news article or headline into the web interface
2. The text is sent to the FastAPI backend via a POST request
3. The trained model predicts whether the text is **FAKE** or **REAL**
4. A confidence score is calculated using the model's decision function
5. The result is displayed instantly on the page

---

## Setup & Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/fake-news-detector.git
cd fake-news-detector
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Train the model

Run this first — it generates `model/model.pkl` which the server needs.

```bash
python train.py
```

### 4. Start the server

```bash
python main.py
```

The app will be running at **http://localhost:8000**

---

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | Serves the web interface |
| POST | `/predict` | Returns FAKE/REAL label + confidence score |

### Example POST request

```bash
curl -X POST http://localhost:8000/predict \
  -H "Content-Type: application/json" \
  -d '{"text": "BREAKING: Scientists expose government conspiracy!!!"}'
```

### Example response

```json
{
  "label": "FAKE",
  "confidence": 87.45
}
```

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | Python, FastAPI, Uvicorn |
| ML Model | scikit-learn, joblib |
| Frontend | HTML, CSS, JavaScript |
| Templating | Jinja2 |

---

## requirements.txt

```
fastapi
uvicorn
jinja2
scikit-learn
joblib
numpy
python-multipart
```

---
