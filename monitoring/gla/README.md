# Grafana + Loki + Alloy on AWS EC2

This repository accompanies the video tutorial where I deploy a **Grafana + Loki + Alloy** centralized logging stack on an **AWS EC2 instance** using Docker.

The video demonstrates how to collect logs from:

* 📂 Filesystem logs
* 🐳 Live Docker container logs

making debugging and observability simple and efficient.

---

## 🎥 Video Tutorial

[![Deploy Grafana + Loki + Alloy on AWS EC2](https://img.youtube.com/vi/pLugtYKS_DA/0.jpg)](https://youtu.be/pLugtYKS_DA)

👉 **Watch on YouTube**
[https://youtu.be/pLugtYKS_DA](https://youtu.be/pLugtYKS_DA)

---

## ✨ Key Takeaways

* Deploying Grafana, Loki, and Alloy using **Docker Compose**
* Collecting logs from the **filesystem** and **Docker containers**
* Setting up an **AWS EC2 instance** and connecting via **SSH**

---

## 📦 Resources

* **Main DevOps Labs Repository**
  [https://github.com/The-Quick-Desk/tqd-devopslabs.git](https://github.com/The-Quick-Desk/tqd-devopslabs.git)

* **Grafana + Loki + Alloy Stack**
  [https://github.com/The-Quick-Desk/tqd-devopslabs/tree/main/monitoring/gla](https://github.com/The-Quick-Desk/tqd-devopslabs/tree/main/monitoring/gla)

* 🔔 **Subscribe for more DevOps content**
  [https://www.youtube.com/@TQDLite](https://www.youtube.com/@TQDLite)
  [https://www.youtube.com/@thequickdesk25](https://www.youtube.com/@thequickdesk25)

---

## 🚀 Getting Started

### Prerequisites

* Docker
* Docker Compose

### Usage

1. **Clone the repository**

   ```bash
   git clone https://github.com/The-Quick-Desk/tqd-devopslabs.git
   cd tqd-devopslabs/monitoring/gla
   ```
###### MAKE SURE TO CHANGE THE CONFIG FILES AS PER YOUR REQUIREMENTS : .env & multi-docker-loki.yaml OR .env & s3-default.yaml
###### As they need the S3 bucket name and region & .env for version.

2. **Start the stack**

   ```bash
   docker-compose up -d
   ## IF WANTED MULTI LOKI
   docker-compose -f docker-compose.multi-loki.yml up -d
   ```
3. **Access Grafana**

   ```
   http://localhost:3000
   ```

---