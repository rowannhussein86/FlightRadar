# ✈️ FlightRadar 2025 - Real-Time Flight Simulation & Visualization

FlightRadar 2025 is a **dynamic flight tracking simulation** designed to mimic real-world airline data pipelines. 
It allows you to simulate flights across the globe, stream data in real-time, process events, and visualize flight positions interactively.

---

## 🌍 Project Overview

- Simulates flights with **origin and destination coordinates**.
- Generates realistic flight events using Python's **Faker** library.
- Streams flight events through **Apache Kafka** for real-time data flow.
- Processes incoming data with **Spark Structured Streaming** for transformation and enrichment.
- Stores processed flight events in **PostgreSQL**.
- Visualizes live flight data on an **interactive Streamlit dashboard**.

---

## 🛠 Technologies & Tools

| Layer | Technology | Purpose |
|-------|------------|--------|
| Data Generation | Python (Faker) | Simulate flight events |
| Streaming | Apache Kafka | Real-time event streaming |
| Processing | Apache Spark | Transform & enrich flight events |
| Storage | PostgreSQL | Persist flight records |
| Visualization | Streamlit | Interactive flight dashboard |
| Deployment | Docker Compose | Containerized orchestration |

---

## ⚡ Features

- **Realistic Flight Simulation:** Origin/destination, departure/arrival times, and flight status.
- **Real-Time Streaming:** Events flow through Kafka topics instantly.
- **Data Transformation:** Spark enriches data before storage.
- **Persistent Storage:** All events saved in PostgreSQL for analytics.
- **Interactive Dashboard:** Live flight positions and status indicators.
- **Modular & Extensible:** Easy to add more flights or integrate with other tools.

---
Project Quick Start Guide

🚀 Quick Start
## 🚀 Quick Start

1. **Start Docker Services**
```bash
docker-compose up -d
```
2. **Verify running containers**
Make sure Kafka, PostgreSQL, Spark, and Streamlit containers are up.
```bash
docker ps
```
3. **Run Python Producer**  
- Open `scripts/producer.ipynb` (or `scripts/producer.py`)  
- Execute the notebook/script to generate flight events and send them to Kafka topic `flights`

4. **Monitor Kafka Topic**  
- Open Kafka UI at [http://localhost:8090](http://localhost:8090)  
- Confirm that messages are being produced to topic `flights`

5. **Set Up PostgreSQL**  
- Open pgAdmin at [http://localhost:8085](http://localhost:8085)  
- Login with:  
  - Email: `admin@admin.com`  
  - Password: `admin`  
- Create a new server connection:  
  - Name: `postgres_general`  
  - Host: `postgres`  
  - Port: `5432`  
  - Username: `admin`  
  - Password: `admin`

- Create database flight_radar
```
CREATE DATABASE flight_radar;
Create flights table:

CREATE TABLE flights (
    flight_id VARCHAR PRIMARY KEY,
    origin TEXT,
    destination TEXT,
    status TEXT,
    departure_time BIGINT,
    arrival_time BIGINT
);
```


6-**Run Spark Streaming**
Open scripts/spark_streaming.ipynb
Ensure PostgreSQL driver is installed:
```
pip install psycopg2-binary
```
Execute the notebook to process events from Kafka and store them into PostgreSQL

7-**Launch Streamlit Dashboard**
```
streamlit run scripts/dashboard.py
```
Access at [http://localhost:8501](http://localhost:8501)
Explore the real-time flight map and flight statuses

8-**Stop and Clean Up**
```
docker-compose down -v
```

## 📊 Data Pipeline Flow
Python Producer (Faker)   ->   Kafka Topic: flights   ->   Spark Structured Streaming   ->   PostgreSQl    ->   Streamlit Dashboard
