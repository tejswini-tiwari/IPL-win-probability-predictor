# 📄 README.md

```md
![Docker](https://img.shields.io/badge/Docker-Containerized-blue)
![FastAPI](https://img.shields.io/badge/FastAPI-Backend-green)
![Streamlit](https://img.shields.io/badge/Streamlit-Frontend-red)
![ML](https://img.shields.io/badge/MachineLearning-ScikitLearn-orange)
````

```md
# 🏏 IPL Live Win Probability Predictor

A **Machine Learning powered IPL match win predictor** deployed using a **FastAPI backend** and **Streamlit frontend**, fully containerized with **Docker** and runnable using **Docker Compose**.

This project predicts the winning probability of the batting and bowling teams based on live match conditions.

---

## 🚀 Features

✅ Live win probability prediction  
✅ FastAPI ML inference API  
✅ Interactive Streamlit dashboard UI  
✅ Dockerized microservice architecture  
✅ One-command deployment using Docker Compose  
✅ Production-style frontend ↔ backend communication  

---

## 🧠 Tech Stack

### Machine Learning
- Scikit-learn
- Logistic Regression
- Pipeline + OneHotEncoder

### Backend
- FastAPI
- Uvicorn
- Pandas
- Pickle (model loading)

### Frontend
- Streamlit
- Custom CSS dashboard UI

### DevOps / Deployment
- Docker
- Docker Compose
- Docker Hub

---

## 🏗️ Project Architecture

```

┌──────────────────────┐
│     Streamlit UI     │
│      (Frontend)      │
│   Port: 8501         │
└───────────┬──────────┘
│ HTTP Request
▼
┌──────────────────────┐
│      FastAPI API     │
│     ML Prediction    │
│      Port: 8000      │
└──────────────────────┘

````

Frontend communicates with backend using Docker internal networking:

```

http://backend:8000/predict

```

---

## 📂 Project Structure

```

IPL-Win-Predictor/
│
├── backend/
│   ├── main.py
│   ├── pipe.pkl
│   ├── requirements.txt
│   └── Dockerfile
│
├── frontend/
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
│
└── docker-compose.yml

````

---

## ⚙️ API Endpoint

### POST `/predict`

#### Request Body

```json
{
  "batting_team": "Mumbai Indians",
  "bowling_team": "Chennai Super Kings",
  "city": "Mumbai",
  "runs_left": 45,
  "balls_left": 30,
  "wickets": 6,
  "target": 180,
  "cur_run_rate": 8.5,
  "req_run_rate": 9.0
}
```

#### Response

```json
{
  "loss": 0.35,
  "win": 0.65
}
```

---

## 🐳 Run Using Docker (Recommended)

### ✅ Prerequisites

Install:

* Docker Desktop
* Docker Compose

---

### ▶️ Run the Application

```bash
docker compose up
```

Docker will automatically:

* Pull frontend image
* Pull backend image
* Start both services

---

### 🌐 Open Application

Frontend:

```
http://localhost:8501
```

Backend API:

```
http://localhost:8000
```

---

## 🧪 Local Development (Optional)

### Backend

```bash
cd backend
pip install -r requirements.txt
uvicorn main:app --reload
```

### Frontend

```bash
cd frontend
streamlit run app.py
```

---

## 🐳 Docker Images

Available on Docker Hub:

* `YOUR_USERNAME/ipl-win-predictor-backend`
* `YOUR_USERNAME/ipl-win-predictor-frontend`

---

## 🔥 Key Learning Outcomes

* ML model deployment using FastAPI
* Containerized microservices architecture
* Docker networking between services
* Production-style ML API design
* Frontend ↔ Backend communication

---

## 📸 Demo

(Add screenshots here)

```
![App Screenshot](screenshots/app.png)
```

---

## 👩‍💻 Author

**Tejswini Tiwari**

Integrated B.Tech + M.Tech (IT)
International Institute of Professional Studies, DAVV

---

## ⭐ Future Improvements

* Live match API integration
* Kubernetes deployment
* CI/CD pipeline
* Cloud deployment (AWS/GCP)

---

## 📜 License

MIT License

```
