# Kafka Docker Setup and Usage

This repository demonstrates how to set up Kafka using Docker, create a topic, and send and receive messages.

## Prerequisites
Docker and Docker Compose should be installed.

## Getting Started

**1. Start Kafka and Zookeeper Containers**

- Create a docker-compose.yml file with the following content
- Start the Kafka and Zookeeper containers using Docker Compose:
```
docker-compose up -d
```

**2. Access Kafka Container and Create Topic**

- Find the Kafka container ID using docker ps and access the container:
```
docker ps
docker exec -it <KAFKA_CONTAINER_ID> bash
```
- Create a Kafka topic named test_topic:
```
kafka-topics --create --topic test_topic --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1
```

**3. Send Messages to the Topic**

Start a Kafka producer and send messages to test_topic

Type your messages and press Enter to send them.
```
kafka-console-producer --topic test_topic --bootstrap-server localhost:9092
```

**4. Consume Messages from the Topic**
In another terminal, access the Kafka container again and start a Kafka consumer to listen to test_topic:

You will see all messages sent to the topic from the beginning.
```
docker exec -it <KAFKA_CONTAINER_ID> bash
kafka-console-consumer --topic test_topic --bootstrap-server localhost:9092 --from-beginning
```



