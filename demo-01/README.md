# 🧪 Demo 1: Message Queue vs Data Streaming

In that lab, we see the **behavior difference** between message queue and data streaming with commands.

---

## 1. Create a Topic (Data channel)

### What is a Topic?

Topics in Kafka serve the same purpose as a data repository—providing storage, organization, and categorization for data trafficking through the system.

Example:
```bash
/opt/kafka/bin/kafka-topics.sh --create --topic eventos-ia --partitions 3 --bootstrap-server localhost:9092
```

---

## 2. Scenario A - Message Queue behavior

Divide the terminal in three columns (two consumers and one producer) and define a `Consumer Group`. The result is messages to be sliced up and distributed exclusively among the workers (rebalancing):

*Note: in my tests, the messages only are printed in one of the consumers*

* **Worker A:**
```bash
/opt/kafka/bin/kafka-console-consumer.sh --topic eventos-ia --bootstrap-server localhost:9092 --group minha-fila
```

* **Worker B:**
```bash
/opt/kafka/bin/kafka-console-consumer.sh --topic eventos-ia --bootstrap-server localhost:9092 --group minha-fila
```

* **Producer:**
```bash
/opt/kafka/bin/kafka-console-producer.sh --topic eventos-ia --bootstrap-server localhost:9092
```

## 3. Scenario B: Data Streaming behavior
Divide the terminal in two columns. The sent data (step 2) it is replicated in its entirely for all listeners:

*Note: this means all the data sent in both consumers of a group will be printed*

* **Consumer:**
```bash
/opt/kafka/bin/kafka-console-consumer.sh --topic eventos-ia --from-beginning --bootstrap-server localhost:9092
```

* **Producer:**
```bash
/opt/kafka/bin/kafka-console-producer.sh --topic eventos-ia --bootstrap-server localhost:9092
```

---

## 🔍 Conclusion

After running the commands, we can clearly see the fundamental difference between these two concepts. **Message Queues** handle ephemeral, point-to-point data—once a message is read by a consumer, it is processed and deleted from the queue . On the other hand, **Data Streaming** retains a persistent and immutable log of all past actions, allowing multiple consumers to replay the entire history at their own pace.
