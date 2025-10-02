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
## 🚀 Quick Start

```markdown
1. **Start Docker Services**
```bash
docker-compose up -d

2. **Verify running containers**
```bash
docker ps
Make sure Kafka, PostgreSQL, Spark, and Streamlit containers are up.
