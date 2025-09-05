# event-driven-data-pipeline
Event-Driven Data Pipeline

A demo microservices-based data pipeline showcasing event-driven architecture with REST API ingestion, Kafka streaming, and MongoDB persistence. The project demonstrates how to decouple services for scalability and real-time processing.

 Features:

REST API service to ingest data with Kafka as the event broker

Worker service to consume and persist data into NoSQL database

Asynchronous, decoupled communication between services

Metrics exposed for monitoring with Prometheus/Grafana

Containerized with Docker Compose for local orchestration

Tech Stack:

Language: Java (Spring Boot) 

Event Broker: Apache Kafka

Database: DynamoDB

Monitoring: Prometheus, Grafana

Containerization: Docker & Docker Compose

Architecture:
flowchart LR
  A[REST API Service] -->|Publish Event| B[Kafka Topic]
  B --> C[Worker Service]
  C -->|Persist| D[(DynamoDB)]
  C --> E[Metrics / Prometheus]

Getting Started:
Prerequisites:

Docker & Docker Compose installed

(Optional) Java 17+ or Python 3.9+ for local development

Run with Docker Compose
# Clone repo
git clone https://github.com/<your-username>/event-driven-data-pipeline.git
cd event-driven-data-pipeline

# Start services
docker-compose up --build

API Example

POST /api/v1/events

{
  "userId": "12345",
  "action": "purchase",
  "amount": 49.99,
  "timestamp": "2025-09-01T10:00:00Z"
}

Monitoring & Metrics

Prometheus scrapes metrics from the Worker service (e.g., events processed/sec, queue lag).

Grafana dashboard visualizes system performance.

To access Grafana:

http://localhost:3000

Project Structure:
event-driven-data-pipeline/
│── api-service/             # REST API service
│── worker-service/          # Kafka consumer + MongoDB writer
│── monitoring/              # Prometheus + Grafana configs
│── docker-compose.yml       # Orchestration
│── README.md                # Project documentation

Future Improvements:

Add authentication/authorization on API service

Implement dead-letter queue for failed messages

Deploy to AWS using MSK (Managed Kafka) + DynamoDB + CloudWatch

Add CI/CD pipeline with GitHub Actions

Author:

Prathyusha Yetukuri

LinkedIn: [linkedin.com/in/yourname](https://www.linkedin.com/in/prathyusha-yetukuri-681b3656/)

GitHub: https://github.com/PrathyushaY2493
