# Realtime Data Streaming | End-to-End Data Engineering Project

## 📖 Table of Contents
- [Introduction](#Project-Overview)
- [System Architecture](#system-architecture)
- [What You'll Learn](#what-youll-learn)
- [Technologies](#technologies)
- [Getting Started](#getting-started)
- [Watch the Video Tutorial](#watch-the-video-tutorial)

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
- 🔁 **Automated Orchestration : **Scheduled data fetching and streaming via Apache Airflow
- 📡 **Real-Time Ingestion : **Stream user data in real time using Apache Kafka
- ⚙️ **Stream Processing : **Live data transformation with Apache Spark Structured Streaming
- 🗃️ **Scalable Storage : **Persist data in Apache Cassandra, a distributed NoSQL database
- 🧭 **Monitoring & Schemas : **Manage and track streams with Kafka Control Center & Schema Registry




## 🤝 Author
Project built and documented by Adil Inthiyaz Shaik.
