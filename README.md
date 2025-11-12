# 🎬 Video Recommendation System — From Prototype to Production

A modular, end-to-end **Recommendation System** designed to evolve from a laptop-scale prototype to a **cloud-scale real-time recommender**.  
Built with **Python, FastAPI, Annoy/Faiss, XGBoost, MLflow, and Docker**, this project demonstrates the full lifecycle — data simulation → modeling → deployment → scaling.

---

## 🧠 Project Overview

This system mimics a YouTube-style recommendation workflow, consisting of:
1. **Candidate Generation** (wide recall)
2. **Ranking Model** (precision scoring)
3. **Feedback Loop + Retraining**
4. **API Serving + Caching**
5. **Load Testing + Real-Time Scaling**

The design emphasizes **clarity, modularity, and production readiness** — suitable for inclusion in an engineering portfolio or interview presentation.

---

## 🗂️ Repository Structure

```
video-recommender/
│
├── services/           # Candidate, ranking, feedback, and API services
├── data/               # Interactions, features, and feedback
├── model_repo/         # Versioned trained models
├── configs/            # Model + environment configs
├── scripts/            # Retraining and feature update jobs
├── docker/             # Docker and Compose files
├── tests/              # PyTest-based validation suite
└── notebooks/          # Jupyter exploration & experimentation
```

---

## 📖 Documentation Index (GitHub Wiki)

| Step | Page | Description |
|------|------|-------------|
| 🏠 | [Home](../../wiki/Home) | Project intro, architecture, and milestones |
| 1️⃣ | [Data Simulation](../../wiki/Step1_DataSimulation) | Generate synthetic user–video interactions |
| 2️⃣ | [Candidate Generation](../../wiki/Step2_CandidateGeneration) | ANN-based retrieval using Annoy/Faiss |
| 3️⃣ | [Ranking Model](../../wiki/Step3_RankingModel) | XGBoost-based ranking and evaluation |
| 4️⃣ | [End-to-End Flow](../../wiki/Step4_EndToEnd) | Pipeline orchestration from input to output |
| 5️⃣ | [Feedback Loop](../../wiki/Step5_FeedbackLoop) | Logging user behavior and retraining strategy |
| 6️⃣ | [APIs](../../wiki/Step6_APIs) | FastAPI microservice exposing recommendations |
| 7️⃣ | [Project Structure](../../wiki/Step7_ProjectStructure) | Modular repo layout and coding standards |
| 8️⃣ | [Tooling](../../wiki/Step8_Tooling) | Docker, MLflow, Dask, CI/CD setup |
| 9️⃣ | [Load Testing](../../wiki/Step9_LoadTesting) | Benchmarking with Locust and Prometheus |
| 🔟 | [Scaling to Real-Time Systems](../../wiki/Step10_PortfolioPolish) | Enterprise-grade architecture and scaling roadmap |

---

## ⚙️ Quickstart

### 1. Clone the Repo
```bash
git clone https://github.com/<your-username>/video-recommender.git
cd video-recommender
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the API
```bash
uvicorn services.api_service:app --reload --port 8000
```

### 4. Try the Endpoint
```bash
curl -X POST "http://127.0.0.1:8000/recommend"      -H "Content-Type: application/json"      -d '{"user_id": 42, "top_n": 5}'
```

---

## 🧰 Tooling Highlights
| Tool | Purpose |
|------|----------|
| **FastAPI** | Serve real-time recommendations |
| **Annoy / Faiss** | Vector search for candidate retrieval |
| **XGBoost / LightGBM** | Ranking models |
| **Docker + Compose** | Containerization and orchestration |
| **Dask** | Parallel feature computation |
| **MLflow** | Experiment tracking and model registry |
| **Prometheus + Grafana** | Monitoring and observability |
| **Airflow / Kubeflow** | Automated retraining pipelines |

---

## 📈 Key Learnings
- Designed a two-stage recommendation system (recall + precision)
- Implemented retraining and feedback logging loops
- Deployed a FastAPI inference service with Redis caching
- Conducted load testing (Locust + Prometheus)
- Scaled the design to handle **1K+ RPS** with cloud-native components

---

## 🌐 Live Demo (Optional)
Once deployed:
```
https://<your-domain-or-load-balancer>/docs
```
Interactive API documentation available via Swagger UI.

---

## 🧩 Author
**Divya Dronamraju**  
Generative AI & ML Engineer  
Georgia Tech MS Analytics | Infosys  

---

## 🏁 What’s Next
- Integrate **deep two-tower models** for embeddings  
- Add **contextual bandits** for personalization feedback  
- Extend **multi-objective ranking** (CTR + diversity)  
- Deploy to **Azure / GCP / AWS** with autoscaling  

---

> 📘 *“From notebook to production — this project shows the real engineering behind machine learning systems.”*
