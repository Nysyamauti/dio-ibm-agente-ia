# 🚀 DIO Bootcamp - IBM Confluent: **Final Project** - 💸 Payment Pipelines

## 🔎 Challenge Context
The final challenge for this bootcamp is to build a real-time data pipeline and intelligent applications using Apache Kafka, Confluent Cloud, Apache Flink, and AI.

> **Note:** During class demonstrations, the DIO instructor uses the **Confluent Data Streaming Platform**. However, I chose to run the entire architecture locally using only Docker.

## ❗ Setup

### 💻 How to Run
1. Install and open **Docker Desktop**.
2. *(Optional)* In VSCode, install the official **Docker extension** by Microsoft to easily monitor containers and logs.
3. Run the [`docker-compose.yml`](./docker-compose.yml) file from the root directory to spin up the ecosystem:
```bash
cd final-proj
docker compose up -d
```
4. If any error occurs or you want to stop and clean up the environment, run:
```bash 
docker compose down
```