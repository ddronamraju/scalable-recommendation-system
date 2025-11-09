# scalable-recommendation-system
A two-stage video recommendation system combining Annoy for fast candidate generation and XGBoost for ranking user engagement. Includes a feedback-driven retraining loop and modular FastAPI microservices, optimized for scalability and efficient execution on a personal laptop.

## 🚀 Scaling This Project to Production

While this project runs efficiently on a personal laptop, the same architecture can be scaled to production environments with a few key upgrades:

- **Candidate Generation → Distributed ANN:**  
  Replace the local Annoy index with a **vector database** (e.g., FAISS, Milvus, Pinecone) that supports sharding, replication, and caching for sub-50 ms retrieval latency.

- **Ranking → Managed Model Serving:**  
  Serve the XGBoost ranker via **MLflow**, **Vertex AI**, or **SageMaker** endpoints.  
  Fetch real-time features from a **Feature Store** (Feast, Redis) to maintain offline/online parity.

- **Feedback → Streaming Pipeline:**  
  Use **Kafka**, **Flink**, or **Spark Streaming** to collect user feedback in real time and trigger automatic retraining on fresh interaction data.

- **Deployment → Containers & Orchestration:**  
  Containerize each microservice with **Docker** and deploy to **Kubernetes**, enabling autoscaling and independent resource management per service.

- **Observability → Metrics & Tracing:**  
  Integrate **OpenTelemetry**, **Prometheus**, and **Grafana** dashboards for end-to-end latency (p95), error rates, and cache hit ratios.

- **Experimentation → A/B Testing & Exploration:**  
  Implement an **A/B testing** framework and use **Thompson Sampling** or ε-greedy policies to balance recommendation quality and novelty.

- **Governance → Registry, CI/CD & Compliance:**  
  Track model versions in a **Model Registry**, automate builds with **GitHub Actions**, and apply **data retention & PII masking** policies for compliance.

---

> 💡 *This section serves as a roadmap for turning the local prototype into a cloud-ready, scalable recommendation system that aligns with real-world ML engineering practices.*

