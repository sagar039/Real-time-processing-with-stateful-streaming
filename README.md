# Real-Time Order Processing with Stateful Streaming using Apache Spark & Kafka

## Overview
This project implements a **real-time, stateful streaming pipeline** for order-payment matching using **Apache Spark Structured Streaming, Kafka, MongoDB, and Google Cloud Platform (GCP)**. The system processes streaming events with **exactly-once guarantees** and stores results in MongoDB for real-time analytics.

## Architecture
1. **Data Ingestion:**
   - Orders and payments are generated as **real-time events** and published to Kafka topics.
2. **Stateful Processing with Spark:**
   - Used **applyInPandasWithState** to match orders with payments, ensuring handling of **out-of-order events**.
   - Implemented **deduplication** to avoid duplicate processing.
3. **Storage & Analytics:**
   - Processed data is stored in **MongoDB** for real-time insights.
   - Supports dashboard visualization using MongoDB’s built-in tools.
4. **Cloud Integration (Optional):**
   - The pipeline runs on **GCP Dataproc**, utilizing **auto-scaling and fault-tolerant processing**.

## Tech Stack
- **Streaming Platform:** Apache Kafka
- **Data Processing:** Apache Spark Structured Streaming (PySpark)
- **Storage:** MongoDB
- **Cloud Platform:** Google Cloud Platform (GCP Dataproc)
- **Programming Language:** Python

## Features
- Real-time event-driven order-payment matching.
- Handles **out-of-order** events using **stateful processing**.
- Ensures **exactly-once processing** with Spark’s checkpointing and Kafka durability.
- MongoDB integration for **real-time analytics**.
- Fault-tolerant and **scalable** on **GCP Dataproc**.

### Prerequisites
- Python 3.x
- Apache Kafka
- Apache Spark (Structured Streaming enabled)
- MongoDB
- Google Cloud SDK (Optional, if running on GCP)

## Future Enhancements
- Implement a **dashboard with Grafana** for real-time visualization.
- Expand to handle multiple event types (refunds, cancellations, etc.).
- Deploy on **AWS/GCP with Kubernetes** for high availability.
