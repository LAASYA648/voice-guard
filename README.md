# voice-guard
VoiceGuard – Dockerized Inference Environment

📌 Overview

This repository contains a Dockerized Machine Learning Inference API built using FastAPI. The service exposes REST endpoints for health checks and real-time predictions, with the ML model safely loaded and executed inside a Docker container.

The project demonstrates how to containerize an inference service with clear build and run instructions, following best practices suitable for production, MLOps, and deployment workflows.


---

🛠️ Tech Stack

Language: Python 3.10

Framework: FastAPI

ASGI Server: Uvicorn

Containerization: Docker

Base Image: python:3.10-slim

API Docs: Swagger UI (OpenAPI)

Deployment: AWS EC2 (Dockerized)



---

📂 Project Structure

fastapi-docker/
├── app/
│   └── main.py
├── requirements.txt
├── Dockerfile
└── README.md


---

🐳 Docker Build & Run Instructions

Build the Docker Image

docker build -t fastapi-inference .

Run the Container

docker run -d -p 8000:80 fastapi-inference

The container listens on port 80

The application is accessible via port 8000 on the host



---

🚀 Access the Application

Swagger UI

http://<public-ip>:8000/docs


---

🧪 API Endpoints

Health Check

GET /health

Response

{
  "status": "ok"
}

Prediction Endpoint

POST /predict

Request

{
  "text": "This is a good example"
}

Response

{
  "prediction": "positive",
  "confidence": 0.9
}


---

☁️ Deployment Notes (AWS EC2)

Allow inbound traffic on port 8000 in the EC2 Security Group

Docker container exposes port 80

Uvicorn is bound to 0.0.0.0 for external access



---

⚙️ Key Implementation Details

Lazy loading of the ML model to avoid startup failures

Lightweight Docker image for faster builds and deployments

Health endpoint for monitoring and orchestration readiness

API designed to be CI/CD and Kubernetes compatible



---

✅ Task Status

✔ Inference API successfully containerized
✔ Docker image built and tested
✔ Clear build, run, and deployment instructions provided


---

📈 Future Enhancements

Kubernetes deployment with Service & Ingress

CI/CD pipeline integration

Model versioning support

Authentication and request validation



---

👤 Author

Laasya Patale
Dockerized Inference Environment – VoiceGuard Task
