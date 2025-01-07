# Kafka Producer and Consumer in Node.js

This project demonstrates a simple Kafka Producer and Consumer implementation using Node.js and the @confluentinc/kafka-javascript library. 
The producer sends messages to a specified Kafka topic, and the consumer reads messages from the same topic.

## Features

- Producer: Sends a single message (key and value) to a Kafka topic.
- Consumer: Listens to the same Kafka topic and logs the consumed messages.
- Graceful Shutdown: Ensures resources are cleaned up on termination (e.g., SIGTERM and SIGINT signals).

## Prerequisites
Node.js: Ensure Node.js is installed (v18+ recommended).
Kafka Broker: A running Kafka instance (e.g., local or Confluent Cloud).
Client Properties File: A configuration file (client.properties) containing Kafka connection settings.

```bash
npm install @confluentinc/kafka-javascript
```
## Create a client.properties 
file: The client.properties file should include your Kafka broker configurations:

```bash
bootstrap.servers=<broker-url>
sasl.username=<username>
sasl.password=<password>
sasl.mechanism=PLAIN
security.protocol=SASL_SSL
```
Replace <broker-url>, <username>, and <password> with your Kafka details.

## Code Overview
- Key Functions
  - readConfig(fileName): Reads and parses the client.properties configuration file.
  - produce(topic, config):
- Creates a Kafka producer.
  - Sends a single message (key = "key", value = "value") to the specified topic.
- consume(topic, config):
  - Creates a Kafka consumer.
  - Subscribes to the specified topic and logs each consumed message.

## Main Function
- The main() function reads the Kafka configuration from client.properties, specifies a topic (topic_emi), and invokes the produce and consume functions.
