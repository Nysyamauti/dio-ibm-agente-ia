# 🚀 DIO Bootcamp - IBM Confluent: **Final Project** - 💸 Payment Pipelines

## 🔎 Challenge Context
The final challenge for this bootcamp is to build a real-time data pipeline and intelligent applications using Apache Kafka, Confluent Cloud, Apache Flink, and AI.

> **Note:** During class demonstrations, the DIO instructor uses the **Confluent Data Streaming Platform**. However, I chose to run the entire architecture locally using only Docker.

## ❗ Setup

### How to Run
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

## 💻 Expected Output

After running `docker compose up -d`, all services should be up and healthy (`docker compose ps`).

```text
NAMES             IMAGE                                   STATUS                   PORTS
kafka-ui          provectuslabs/kafka-ui:latest           Up 8 minutes             0.0.0.0:8080->8080/tcp, [::]:8080->8080/tcp
schema-registry   confluentinc/cp-schema-registry:7.5.0   Up 8 minutes             0.0.0.0:8081->8081/tcp, [::]:8081->8081/tcp
taskmanager       flink:1.18.1-java17                     Up 9 minutes             6123/tcp, 8081/tcp
postgres          postgres:15-alpine                      Up 9 minutes             0.0.0.0:5432->5432/tcp, [::]:5432->5432/tcp
jobmanager        flink:1.18.1-java17                     Up 9 minutes (healthy)   0.0.0.0:8082->8081/tcp, [::]:8082->8081/tcp
kafka             confluentinc/cp-kafka:7.5.0             Up 9 minutes (healthy)   0.0.0.0:9092->9092/tcp, [::]:9092->9092/tcp, 0.0.0.0:29092->29092/tcp, [::]:29092->29092/tcp
```

### Service Endpoints
* **Kafka UI:** `http://localhost:8080`
* **Apache Flink Dashboard:** `http://localhost:8082`
