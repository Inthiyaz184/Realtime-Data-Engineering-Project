# Realtime Data Streaming | End-to-End Data Engineering Project

## 📖 Table of Contents
- [Introduction](#Project-Overview)
- [System Architecture](#system-architecture)
- [Tool-wise Section Flow](#what-youll-learn)
- [Technologies](#technologies)
- [Key Features](#key-features)

## 🚀 Project Overview

This project serves as a comprehensive guide to building an end-to-end data engineering pipeline. It covers each stage from data ingestion to processing and finally to storage, utilizing a robust tech stack that includes Apache Airflow, Python, Apache Kafka, Apache Zookeeper, Apache Spark, and Cassandra. Everything is containerized using Docker for ease of deployment and scalability.

## 🧱 System Architecture

![System Architecture](https://github.com/airscholar/e2e-data-engineering/blob/main/Data%20engineering%20architecture.png)

The project is designed with the following components:

- **Data Source**: We use `randomuser.me` API to generate random user data for our pipeline.
- **Apache Airflow**: Responsible for orchestrating the pipeline and storing fetched data in a PostgreSQL database.
- **Apache Kafka and Zookeeper**: Used for streaming data from PostgreSQL to the processing engine.
- **Control Center and Schema Registry**: Helps in monitoring and schema management of our Kafka streams.
- **Apache Spark**: For data processing with its master and worker nodes.
- **Cassandra**: Where the processed data will be stored.

## 🔧 Tool-wise Section Flow

### 1. 🧑‍💻 Data Source – `randomuser.me` API
- **Purpose:** Generates random user profile data (name, email, location, etc.)
- **Role in Pipeline:** Acts as the real-time external data provider.
- **Trigger:** Called periodically by Apache Airflow to fetch fresh user data.

---

### 2. 🪄 Apache Airflow – Orchestration Layer
- **Purpose:** Automates and schedules the entire pipeline.
- **What It Does:**
  - Schedules DAGs to hit the randomuser.me API.
  - Stores raw data into **PostgreSQL** (temporary staging).
- **Why It’s Important:** Ensures all parts of the pipeline are triggered and executed in the correct sequence.

![Screenshot 2025-04-19 221304](https://github.com/user-attachments/assets/32fbc994-ea5e-4862-b99c-386286f41337)


---

### 3. 🗃️ PostgreSQL – Temporary Staging Storage
- **Purpose:** Temporary storage for raw data fetched by Airflow.
- **What It Does:**
  - Acts as a bridge between ingestion and streaming layers.
  - Kafka connector fetches data from PostgreSQL.

---

### 4. 🛰️ Apache Kafka & 🧭 Apache Zookeeper – Streaming Layer
- **Purpose:** Real-time streaming backbone.
- **What It Does:**
  - Kafka streams data from PostgreSQL to Spark.
  - Zookeeper manages and coordinates Kafka brokers.
- **Additional Components:**
  - **Kafka Connect:** Connects PostgreSQL with Kafka.
  - **Schema Registry:** Manages Avro schemas for message serialization.
  - **Kafka Control Center:** Helps monitor Kafka topics, throughput, consumer lag, etc.

![kafka_console](https://github.com/user-attachments/assets/1c956c27-676e-42d4-b1e1-021e1b968171)


---

### 5. ⚡ Apache Spark – Real-Time Stream Processing
- **Purpose:** Performs structured streaming & transformation.
- **What It Does:**
  - Reads real-time data from Kafka topics.
  - Parses and transforms raw JSON/Avro data into a structured format.
  - Pushes cleaned/structured data to Cassandra.
 
![Screenshot 2025-04-19 221845](https://github.com/user-attachments/assets/4096ce3d-88e6-4365-8d70-fc1ef7f8e310)


---

### 6. 🗄️ Apache Cassandra – Final Storage
- **Purpose:** Distributed NoSQL database for storing processed data.
- **What It Does:**
  - Receives cleaned data from Spark.
  - Provides high availability and scalability for querying processed user profiles.

---

### 7. 🐳 Docker – Containerization
- **Purpose:** Simplifies deployment and scaling.
- **What It Does:**
  - Every component (Airflow, Kafka, Spark, Cassandra, etc.) runs in isolated containers.
  - Ensures reproducibility and easy environment setup.

---

## ⚙️ Tools & Technologies Used

- Apache Airflow
- Python
- Apache Kafka
- Apache Zookeeper
- Apache Spark
- Cassandra
- PostgreSQL
- Docker

## 🔑 Key Features
- 🔁 **Automated Orchestration :** Scheduled data fetching and streaming via Apache Airflow
- 📡 **Real-Time Ingestion :** Stream user data in real time using Apache Kafka
- ⚙️ **Stream Processing :** Live data transformation with Apache Spark Structured Streaming
- 🗃️ **Scalable Storage :** Persist data in Apache Cassandra, a distributed NoSQL database
- 🧭 **Monitoring & Schemas :** Manage and track streams with Kafka Control Center & Schema Registry




## 🤝 Author
Project built and documented by Adil Inthiyaz Shaik.
