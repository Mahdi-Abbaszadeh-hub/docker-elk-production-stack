# 🚀 Production-Ready ELK Stack Deployment via Docker

Developed by **[Mahdi Abbaszadeh](https://github.com/Mahdi-Abbaszadeh-hub)**

---
## 📄 License & Attribution
This project is open-source and available under the MIT License. You are free to use, modify, and distribute it, provided that **attribution to the original author (Mahdi Abbaszadeh) is maintained** in all copies or substantial portions of the software.
---

## 🛠️ Quick Start (The Professional Way)

Instead of running containers manually, you can spin up the entire stack with a single command using Docker Compose:

```bash
# 1. Start all services in the background
docker compose up -d

# 2. Generate your secure password for the 'elastic' user
docker exec -it elasticsearch bin/elasticsearch-reset-password -u elastic