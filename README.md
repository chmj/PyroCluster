# PyroCluster: Real-Time Big Data Analytics Platform

PyroCluster is a powerful, scalable, and flexible real-time analytics platform built entirely on a modern open-source data stack. It's designed to ingest, process, and visualize massive streams of data with very low latency, providing immediate insights on a live dashboard.

This project serves as a reference architecture for integrating best-in-class technologies to solve complex big data challenges.

---
## 🚀 Core Components

The cluster is built on a "best-of-breed" philosophy, where each component is chosen for its specific strengths in the data lifecycle.

* **Foundation:**
    * **Apache Hadoop (HDFS):** Provides a robust, distributed data lake for long-term storage and batch processing.
    * **Apache YARN:** Acts as the cluster's brain, efficiently managing resources for all processing jobs.
* **Central Message Bus:**
    * **Apache Kafka:** Serves as the high-throughput, fault-tolerant central nervous system, decoupling data ingestion from data processing.
* **Data Ingestion:** (Choose the right tool for the source)
    * **Apache NiFi:** For visual, flow-based programming to manage complex data routing and transformation from diverse sources.
    * **Apache Flume:** For high-volume, reliable log data collection and aggregation into HDFS or Kafka.
    * **Logstash:** For advanced parsing and enrichment of logs and machine-generated data.
* **Real-Time Processing:**
    * **Apache Spark:** The core processing engine. Using Spark Streaming, it performs real-time analytics, aggregations, and transformations on data from Kafka.
* **Visualization & Dashboarding:**
    * **Apache Superset:** A modern BI tool used to create interactive, real-time dashboards by directly querying the processed data from Spark.

---
## 🏗️ System Architecture

The architecture is designed around a central Kafka bus, which enables a clean separation of concerns and massive scalability.

**Data Flow:**
`Data Sources` ➡️ `Ingestion (NiFi / Flume / Logstash)` ➡️ `Apache Kafka (Message Bus)` ➡️ `Apache Spark (Real-Time Processing on YARN)` ➡️ `Apache Superset (Live Dashboard)`
