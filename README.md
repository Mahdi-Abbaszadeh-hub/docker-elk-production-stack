# 🚀 Production-Oriented ELK Stack Deployment via Docker

Developed and Maintained by **[Mahdi Abbaszadeh](https://github.com/Mahdi-Abbaszadeh-hub)**

---

## 📄 License & Attribution
This project is open-source and available under the **Apache License 2.0**. You are completely free to use, modify, and distribute it, provided that **clear attribution to the original author (Mahdi Abbaszadeh) is maintained** in all copies or substantial portions of the software.

---

This project brings together everything about Docker networking, volumes, and resource management to deploy a real, production-oriented observability stack.

### ❓ What Is ELK?
ELK is the most widely used log aggregation stack in the industry:
*   **Elasticsearch (E):** Stores, indexes, and makes logs searchable. It's a powerful distributed database optimized for full-text search.
*   **Logstash (L):** A data pipeline. It reads logs from sources (files, TCP, message queues), applies filters and transformations, and forwards the processed data to Elasticsearch.
*   **Kibana (K):** A web dashboard. It connects to Elasticsearch and lets you search logs, build visualizations, and create dashboards — all in a browser UI.

---

### 🔄 Data Flow Architecture

```mermaid
graph LR
    App[Your Application] -->|Sends JSON Logs via TCP:5010| Logstash[Logstash:5000]
    Logstash -->|Filters & Mutates| Elasticsearch[Elasticsearch:9200]
    Kibana[Kibana:5601] -.->|Queries & Visualizes| Elasticsearch
    User([Your Browser]) -->|Accesses UI| Kibana
    
    style App fill:#f9f,stroke:#333,stroke-width:2px
    style Logstash fill:#bbf,stroke:#333,stroke-width:2px
    style Elasticsearch fill:#f96,stroke:#333,stroke-width:2px
    style Kibana fill:#9f9,stroke:#333,stroke-width:2px