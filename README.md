# FlightRadar

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

Follow these steps to set up and run the application using Docker, Kafka, PostgreSQL, Spark, and Streamlit.





Start Docker Services

docker-compose up -d



Verify Running Containers

docker ps

Ensure Kafka, PostgreSQL, Spark, and Streamlit containers are running.



Run Python Producer





Open scripts/producer.ipynb (or scripts/producer.py).



Execute the notebook/script to generate flight events and send them to the Kafka topic flights.



Monitor Kafka Topic





Open Kafka UI at http://localhost:8090.



Confirm messages are being produced to the flights topic.



Set Up PostgreSQL





Open pgAdmin at http://localhost:8085.



Log in with:





Email: admin@admin.com



Password: admin



Create a new server connection:





Name: postgres_general



Host: postgres



Port: 5432



Username: admin



Password: admin



Create the flight_radar database:

CREATE DATABASE flight_radar;



Create the flights table:

CREATE TABLE flights (
    flight_id VARCHAR PRIMARY KEY,
    origin TEXT,
    destination TEXT,
    status TEXT,
    departure_time BIGINT,
    arrival_time BIGINT
);



Run Spark Streaming





Open scripts/spark_streaming.ipynb.



Ensure the PostgreSQL driver is installed:

pip install psycopg2-binary



Execute the notebook to process events from Kafka and store them in PostgreSQL.



Launch Streamlit Dashboard

streamlit run scripts/dashboard.py





Access the dashboard at http://localhost:8501.



Explore the real-time flight map and flight statuses.



Stop and Clean Up

docker-compose down -v


## 🚀 Quick Start

1. **Start Docker Services**
```bash
docker-compose up -d

2. **Verify running containers**
```bash
docker ps
Make sure Kafka, PostgreSQL, Spark, and Streamlit containers are up.
