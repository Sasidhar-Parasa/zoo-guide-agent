# 🐾 Zoo Guide Agent – GenAI Academy (ADK + Cloud Run)

## 📘 Overview

This project is part of the **GenAI Academy Codelab**:
**Build and Deploy an ADK Agent on Cloud Run**

We developed a **Zoo Guide AI Agent** using the **Agent Development Kit (ADK)** that answers questions about animals using tools like Wikipedia.

The agent is deployed as a **serverless application on Google Cloud Run**, with containerization handled via **Cloud Build** and stored in **Artifact Registry**.

---

## 🧠 Features

* 🤖 AI-powered Zoo Guide Agent
* 🔎 Tool integration (Wikipedia search)
* ⚙️ Built using Google ADK
* ☁️ Fully deployed on Cloud Run
* 🐳 Automated Docker build via Cloud Build
* 📦 Container storage in Artifact Registry

---

## 📂 Project Structure

```
zoo_guide_agent/
│── .venv/               # Virtual environment
│── __init__.py
│── .env                 # Environment variables
│── agent.py             # Main agent logic
│── requirements.txt     # Dependencies
```

---

## ⚙️ GCP Services Used

This project uses the following Google Cloud services:

* **Cloud Run** – Deploy serverless container
* **Cloud Build** – Build Docker images automatically
* **Artifact Registry** – Store container images
* **Vertex AI** – Power the AI agent
* **Compute Engine** – (Optional) Development environment

---

## 🔌 Required APIs

Make sure the following APIs are enabled in your GCP project:

* Cloud Run API
* Cloud Build API
* Artifact Registry API
* Vertex AI API
* Compute Engine API

Enable them using:

```bash
gcloud services enable run.googleapis.com \
  cloudbuild.googleapis.com \
  artifactregistry.googleapis.com \
  aiplatform.googleapis.com \
  compute.googleapis.com
```

---

## 🚀 How It Works

1. User sends a query (e.g., about animals)
2. ADK agent processes the request
3. Agent uses tools (Wikipedia) to fetch data
4. Response is generated and returned to the user

---

## 🐳 Build & Deployment Flow

### 1️⃣ Build Docker Image (Cloud Build)

```bash
gcloud builds submit --tag gcr.io/YOUR_PROJECT_ID/zoo-guide-agent
```

---

### 2️⃣ Store Image

* Image is stored in **Artifact Registry**

---

### 3️⃣ Deploy to Cloud Run

```bash
gcloud run deploy zoo-guide-agent \
  --image gcr.io/YOUR_PROJECT_ID/zoo-guide-agent \
  --platform managed \
  --region us-central1 \
  --allow-unauthenticated
```

---

## 🧪 Example Queries

* "What do lions eat?"
* "Where can I find polar bears in a zoo?"
* "Tell me about elephants"

---

## 🖥️ Agent Interface

The agent supports:

* Interactive chat interface
* Tool execution tracking (ADK trace view)
* Session-based conversations

---

## 🔐 Authentication & Security

* Uses **IAM roles** for secure service communication
* Recommended roles:

  * Cloud Run Invoker
  * Service Account User

---

## 🧹 Cleanup

To avoid charges:

```bash
gcloud run services delete zoo-guide-agent
```

---

## 📝 Author

**Smitha Kolan**
GenAI Academy – March 2026

---

## 🎯 Summary

This project demonstrates:

* Building AI agents using ADK
* Integrating external tools (Wikipedia)
* Containerizing applications with Docker
* Automating builds with Cloud Build
* Deploying scalable services using Cloud Run

---

## 🚀 Future Improvements

* Add more tools (Maps, Weather APIs)
* Improve UI for end users
* Add authentication layer
* Enhance multi-agent workflows

---

Happy Learning & Building 🚀
