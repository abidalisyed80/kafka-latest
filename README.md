## Kafka Cluster Docker Compose

This repository contains a Docker Compose configuration for setting up a Kafka cluster with multiple brokers, Zookeeper nodes, Kafka Connect, Schema Registry, Control Center, Kafka REST Proxy, Kafka KSQLDB Server, Kafka KSQLDB CLI, Kafka UI, and optional monitoring components.
### Requirements
Before executing `docker-compose up -d` create the required folders and files: 
 1. Create folder /data/files
  ```bash
  sudo mkdir -p /data/files
 ```
 2.  Download all property and WebAdmin GUI files to /data/files
### Services Overview:

- **Zookeeper1 & Zookeeper2**: Zookeeper nodes required for Kafka coordination.
- **Kafka Brokers (kafka-broker0, kafka-broker1, kafka-broker2)**: Kafka brokers forming the core of the cluster.
- **Kafka Connect**: Connects Kafka with external data sources and sinks.
- **Kafka Schema Registry**: Stores and manages Avro schemas for Kafka.
- **Kafka Control Center**: Provides a web interface for managing and monitoring Kafka clusters.
- **Kafka KSQLDB Server & CLI**: Allows querying Kafka topics using SQL-like syntax.
- **Kafka REST Proxy**: Provides RESTful interface to Kafka.
- **Kafka UI**: Web UI for monitoring Kafka topics, consumers, and messages.

### Configuration:

- **Volumes**: Data volumes are mounted for persisting Kafka, Zookeeper, Connect, and Schema Registry data.
- **Networks**: A custom bridge network named kafka-network is used for inter-container communication.
- **Ports**: Exposed ports for accessing Kafka, Control Center, REST Proxy, Schema Registry, KSQLDB Server, KSQLDB CLI, and Kafka UI.

### Instructions:

1. Ensure you have Docker and Docker Compose installed.
2. Clone this repository to your local machine.
3. Navigate to the cloned directory.
4. Run `docker-compose up -d` to start the Kafka cluster.
5. Access various Kafka components via their respective ports (e.g., Control Center: http://localhost:9021, Kafka UI: http://localhost:9080).
6. Customize configuration files and environment variables as needed for your use case.

### Monitoring (Optional):

- Monitoring components such as Kafka exporter for Prometheus, Node Exporter, and cAdvisor are included but commented out. Uncomment and configure them if needed for monitoring Kafka cluster health and performance.

### Contributing:

Feel free to contribute to this repository by submitting pull requests, reporting issues, or suggesting improvements. Your contributions are highly appreciated!

### License:

This project is licensed under the [MIT License](LICENSE). Feel free to use, modify, and distribute it as per the terms of the license.
