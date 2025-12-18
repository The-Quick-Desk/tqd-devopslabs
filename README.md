# Grafana + Loki + Alloy on AWS EC2

In this video, I deploy a Grafana + Loki + Alloy logging stack on an AWS EC2 instance using Docker. You’ll see how to collect logs from both filesystem logs and live Docker containers, making debugging simple and efficient.

## Video Tutorial

[![Deploy Grafana + Loki + Alloy on AWS EC2](https://img.youtube.com/vi/pLugtYKS_DA/0.jpg)](https://youtu.be/pLugtYKS_DA)

[**Watch on YouTube**](https://youtu.be/pLugtYKS_DA)

### Key Takeaways
- Deploying Grafana, Loki, and Alloy using Docker Compose.
- Collecting logs from the filesystem and Docker containers.
- Setting up an EC2 instance and connecting via SSH.

## Resources

- 📦 **GitHub Docker Repository**: All Docker Compose files and configurations used in this video are available here.

- 🔔 **Stay updated**: [Subscribe to TQDLite](https://www.youtube.com/@TQDLite)

## Getting Started

### Prerequisites

- Docker
- Docker Compose

### Usage

1. **Clone the repository** (if you haven't already)
2. **Start the stack**
   ```bash
   docker-compose up -d
   ```
3. **Access Grafana**
   Open your browser and navigate to `http://localhost:3000`.

## Disclaimer

> [!IMPORTANT]
> **Educational Use Only**
>
> This repository is for **educational purposes only**. Any kind of redistribution, sale, or modification is strictly prohibited.
