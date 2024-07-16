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
![Ekran görüntüsü 2024-07-12 173158](https://github.com/user-attachments/assets/d23a5706-40aa-4d4a-9f14-9dca36b49d0d)



**2. Access Kafka Container and Create Topic**

- Find the Kafka container ID using docker ps and access the container:
```
docker ps
docker exec -it <KAFKA_CONTAINER_ID> bash
```
- Create a Kafka topic named test_topic:
```
kafka-topics --create --topic my_topic --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1
```
![Ekran görüntüsü 2024-07-12 180604](https://github.com/user-attachments/assets/10322726-74e0-4bc3-8999-96a75fb667a4)


**3. Send Messages to the Topic**

Start a Kafka producer and send messages to test_topic

Type your messages and press Enter to send them.
```
kafka-console-producer --topic my_topic --bootstrap-server localhost:9092
```
![Ekran görüntüsü 2024-07-12 181030](https://github.com/user-attachments/assets/5f7437e3-df56-4e3d-99ce-9e23b6b3ca26)


**4. Consume Messages from the Topic**
In another terminal, access the Kafka container again and start a Kafka consumer to listen to test_topic:

You will see all messages sent to the topic from the beginning.
```
kafka-console-consumer --topic my_topic --bootstrap-server localhost:9092 --from-beginning
```
![Ekran görüntüsü 2024-07-12 181122](https://github.com/user-attachments/assets/89c16caf-2eeb-409c-8eb0-285826915988)




