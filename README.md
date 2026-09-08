# 🩺 Diabetes Prediction Model – (FastAPI + Docker + K8s)


This project helps you learn **Building and Deploying an ML Model** using a simple and real-world use case: predicting whether a person is diabetic based on health metrics. We’ll go from:

- ✅ Model Training
- ✅ Building the Model locally
- ✅ API Deployment with FastAPI
- ✅ Dockerization
- ✅ Kubernetes Deployment

---

## 📊 Problem Statement

Predict if a person is diabetic based on:
- Pregnancies
- Glucose
- Blood Pressure
- BMI
- Age

We use a Random Forest Classifier trained on the **Pima Indians Diabetes Dataset**.

---

## 🚀 Quick Start

### 1. Clone the Repo

```bash
git clone https://github.com/sandytexc/mlops-project.git
cd mlops-project
```

### 2. Create Virtual Environment

```
apt install python3.12-venv
python3 -m venv .mlops
source .mlops/bin/activate
```

### 3. Install Dependencies

```
pip install -r requirements.txt
```

## Train the Model

```
python train.py
```

## Run the API Locally

```
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

### Sample Input for /predict

```
{
  "Pregnancies": 2,
  "Glucose": 130,
  "BloodPressure": 70,
  "BMI": 28.5,
  "Age": 45
}
```

## Dockerize the API

### Build the Docker Image

```
docker build -t diabetes-prediction-model .
```

### Run the Container

```
docker run -p 8000:8000 diabetes-prediction-model
```
### Push the image to docker hub

```
docker login -u sandytexc
docker tag diabetes-prediction-model:latest sandytexc/diabetes-prediction-model:latest
docker push sandytexc/diabetes-prediction-model:latest
```
## Deploy to Kubernetes

```
kubectl apply -f diabetes-prediction-model-deployment.yaml
```

## Port Forward

```
k port-forward svc/diabetes-api-service 1111:80 --address=0.0.0.0
```



