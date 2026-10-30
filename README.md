# IBM Confluent - Dados em tempo real para agentes de IA

## 🎯 Objective
**Learn and make data pipelines in real time and intelligent aplications with Apache Kafka, Confluent Cloud, Apache Flink and AI.**

---

## 🗺️ Bootcamp Labs Tracing (Practice Module)

This repository is organized into multiple hands-on labs following the step-by-step technical demonstrations from the DIO course.

* [📂 Demo 1: Message Queue vs Data Streaming](demo-01/README.md) — Learning the behavior about traditional queues and real-time event streams.
* [📂 Demo 2: The Kafka log (soon)](#) — Learning about Topics, Partitions and Offsets.

---

## 🛠️ Global Requirements
Before run any lab, make sure if you have:
* **Docker Desktop**
* **VScode** with official Docker extension (Microsoft)

*Note: As alternative, you can use [Confluent Cloud](https://www.confluent.io/get-started/?utm_campaign=tm.ibm_cd.dio-2026q3-brazil-enablement&utm_source=ibm&utm_medium=ibmenablement)*.

---

## 🚀 The primordial step - environment setup
Open your **Powershell** (or Terminal) and run the command below to create and initialize the local Apache Kafka server in Docker:
```bash
docker run -d --name meu-kafka-confluent -p 9092:9092 -e KAFKA_NODE_ID=1 -e KAFKA_PROCESS_ROLES=broker,controller -e KAFKA_LISTENERS=PLAINTEXT://0.0.0.0:9092,CONTROLLER://0.0.0.0:9093 -e KAFKA_ADVERTISED_LISTENERS=PLAINTEXT://localhost:9092 -e KAFKA_CONTROLLER_LISTENER_NAMES=CONTROLLER -e KAFKA_LISTENER_SECURITY_PROTOCOL_MAP=CONTROLLER:PLAINTEXT,PLAINTEXT:PLAINTEXT -e KAFKA_CONTROLLER_QUORUM_VOTERS=1@localhost:9093 -e KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR=1 apache/kafka:latest
```

### Tip
To run the next commands, remember, its necessary put the correct path in terminal:
```bash
cd /opt/kafka/bin
```