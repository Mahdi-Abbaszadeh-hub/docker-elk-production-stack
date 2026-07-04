# 🚀 Production-Oriented ELK Stack Deployment via Docker

Developed and Maintained by **Mahdi Abbaszadeh**

---

## 📄 License & Attribution
This project is open-source and available under the **Apache License 2.0**. You are completely free to use, modify, and distribute it, provided that clear attribution to the original author (Mahdi Abbaszadeh) is maintained in all copies or substantial portions of the software.

This project brings together everything about Docker networking, volumes, and resource management to deploy a real, production-oriented observability stack.

---

## ❓ What Is ELK?
ELK is the most widely used log aggregation stack in the industry:
* **Elasticsearch (E):** Stores, indexes, and makes logs searchable. It's a powerful distributed database optimized for full-text search.
* **Logstash (L):** A data pipeline. It reads logs from sources (files, TCP, message queues), applies filters and transformations, and forwards the processed data to Elasticsearch.
* **Kibana (K):** A web dashboard. It connects to Elasticsearch and lets you search logs, build visualizations, and create dashboards — all in a browser UI.

---

## 🚀 How to Use & Deployment Guide

Follow these simple steps to get your production-ready ELK stack up and running.

### 1️⃣ Prerequisites
Make sure you have the following installed on your system:
* Docker (v20.10+ recommended)
* Docker Compose (v2.0+)

### 2️⃣ Environment Setup
Before running the containers, you need to set up your environment variables. 
1. Copy the `.env.example` file to create a `.env` file:
   ```bash
   cp .env.example .env
---

### 📊 Data Flow Architecture

```mermaid
graph LR
    App[Your Application] -->|Sends JSON Logs via TCP:5010| LS[Logstash :5000]
    LS -->|Filters & Mutates| ES[(Elasticsearch :9200)]
    Browser[Your Browser] -->|Accesses UI:5601| KB[Kibana :5601]
    KB -->|Queries & Visualizes| ES

    style App fill:#3498db,stroke:#2980b9,stroke-width:2px,color:#fff
    style LS fill:#e67e22,stroke:#d35400,stroke-width:2px,color:#fff
    style ES fill:#2ecc71,stroke:#27ae60,stroke-width:2px,color:#fff
    style Browser fill:#9b59b6,stroke:#8e44ad,stroke-width:2px,color:#fff
    style KB fill:#1abc9c,stroke:#16a085,stroke-width:2px,color:#fff
