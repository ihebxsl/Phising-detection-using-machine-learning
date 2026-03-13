# 🎣 Phishing URL Detection using Machine Learning

> **Summer Internship Project @ Tunisie Telecom**  
> A machine learning–powered web application to detect phishing URLs in real time and protect users from data theft.

---

## 📌 Overview

Phishing attacks are among the most prevalent cybersecurity threats, tricking users into visiting malicious websites to steal sensitive data. This project builds an end-to-end solution that automatically classifies URLs as **legitimate or phishing** using machine learning — and exposes the model through a user-friendly web application with a REST API backend.

The project covers the full ML pipeline: data collection and preprocessing, feature engineering, model training and evaluation, and production deployment via Flask.

---

## 🏆 Results

| Metric | Value |
|--------|-------|
| Task | Binary Classification (Phishing vs Legitimate) |
| Best Model | *(e.g. Random Forest / XGBoost — update with your actual best)* |
| Accuracy | *(add your value)* |
| Precision | *(add your value)* |
| Recall | *(add your value)* |
| F1-Score | *(add your value)* |

---

## 🗂️ Project Structure

```
Phising-detection-using-machine-learning/
│
├── data/                   # Raw and processed URL datasets
├── notebooks/              # EDA and model experimentation notebooks
├── models/                 # Saved trained model files
├── src/
│   ├── preprocessing/      # Data cleaning and feature extraction pipelines
│   ├── training/           # Model training and evaluation scripts
│   └── prediction/         # Inference logic for new URLs
├── app/
│   ├── app.py              # Flask application entry point
│   ├── templates/          # HTML frontend templates
│   └── static/             # CSS / JS assets
├── requirements.txt
└── README.md
```

---

## ⚙️ Methodology

### 1. Feature Engineering
URLs are parsed and transformed into structured numerical features, including:
- URL length, number of dots, special characters
- Presence of IP address, HTTPS, suspicious keywords
- Domain age and registration features
- Subdomain depth and redirect count

### 2. Model Training & Evaluation
Multiple classifiers were trained and benchmarked:

| Model | Type |
|-------|------|
| Random Forest | Ensemble |
| XGBoost | Gradient Boosting |
| Logistic Regression | Baseline |
| Decision Tree | Classical ML |

All models evaluated on accuracy, precision, recall, and F1-score using stratified cross-validation.

### 3. Deployment
- **Flask REST API** — accepts a URL as input and returns a real-time phishing/legitimate prediction
- **Web Interface** — simple frontend allowing users to paste a URL and get an instant result

---

## 🛠️ Tech Stack

| Category | Tools |
|----------|-------|
| Language | Python |
| Machine Learning | Scikit-learn |
| Data Processing | Pandas, NumPy |
| Web Framework | Flask |
| Frontend | HTML, CSS, JavaScript |
| Serialization | Pickle / Joblib |
| Version Control | Git, GitHub |

---

## 🚀 Getting Started

### Prerequisites
```bash
Python >= 3.9
pip install -r requirements.txt
```

### Run the Web Application
```bash
cd app
python app.py
```
Then open your browser at `http://localhost:5000`

### Train the Model
```bash
cd src/training
python train.py
```

### Test a URL via API
```bash
curl -X POST http://localhost:5000/predict \
     -H "Content-Type: application/json" \
     -d '{"url": "http://example-suspicious-site.com/login"}'
```

**Response:**
```json
{
  "url": "http://example-suspicious-site.com/login",
  "prediction": "Phishing",
  "confidence": 0.97
}
```

---

## 📊 Key Features

- ✅ Real-time phishing URL classification via web interface and REST API
- ✅ Structured feature extraction pipeline from raw URLs
- ✅ Multi-model benchmarking with cross-validation
- ✅ Lightweight Flask deployment — easy to host or containerize
- ✅ Extensible pipeline for new features or model upgrades

---



---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
