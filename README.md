# 🧠 Titanic Survival Prediction API (Flask + ML + Docker)

This project is a simple Flask-based API that predicts Titanic survival outcomes using a machine learning model. The model was trained using the Titanic dataset with only three features: `Pclass`, `Sex`, and `Age`.

The API accepts JSON data and returns whether a given passenger would have survived.

---

## 📦 Tech Stack

- Python 3.10+
- scikit-learn
- Flask (REST API)
- Docker (containerization)
- Postman (API testing)
- pickle (model serialization)

---

## 📁 Project Structure

.
├── app.py # Flask API

├── titanic.pkl # Trained ML model (pickled)

├── Dockerfile # For containerization

├── requirements.txt # Python dependencies

└── README.md

---

## 🔍 Model Summary

- **Features Used**: `Pclass`, `Sex`, `Age`
- **Preprocessing**:
  - `Sex` was label-encoded (0 for female, 1 for male)
  - Dropped unused columns like `Name`, `Ticket`, etc.
- **Training**:
  - Performed EDA and feature engineering in a separate Jupyter notebook
  - Trained a logistic regression classifier
- **Accuracy**:
  - Achieved X% accuracy on test data _(fill this with your actual result)_

---

## 🚀 Getting Started

### 1. Clone & Setup

```bash
git clone https://github.com/your-username/titanic-flask-api.git
cd titanic-flask-api
```

### 2. Run Locally

```bash
# Create a virtual environment
python -m venv .venv
source .venv/bin/activate   # Or .venv\Scripts\activate on Windows

# Install dependencies
pip install -r requirements.txt

# Run the Flask app
python app.py
API will be available at: http://127.0.0.1:5000/
```

### 🔄 API Usage

`/predict (POST)`

Request JSON:

```json
{
  "Pclass": 2,
  "Sex": 1,
  "Age": 30
}
```

Response:

```yaml
Survival Prediction: 0
```

Where 0 = Did not survive, 1 = Survived

🐳 Docker Instructions

```bash
# Build the image
docker build -t flask-ml-app .

# Run the container
docker run -p 5000:5000 flask-ml-app
```

Test the API using Postman or curl.

### 📬 Testing with Postman

Open Postman

Create a new POST request to http://localhost:5000/predict

In the Body → raw → JSON, enter:

```json
{
  "Pclass": 3,
  "Sex": 0,
  "Age": 22
}
```

Click "Send" and get the prediction.

✅ .gitignore Suggestion

```
.venv/
__pycache__/
*.pkl
Dockerfile
```

📄 License
MIT License. Free to use and modify.

🙌 Acknowledgements
Titanic dataset from Kaggle
scikit-learn, Flask, Docker

