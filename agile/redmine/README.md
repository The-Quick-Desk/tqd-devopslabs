# Redmine on AWS EC2 (Docker)

This repository accompanies a hands-on video tutorial demonstrating how to deploy **Redmine** on an **AWS EC2 instance** using **Docker**, and how to configure **Google OAuth (SSO)** for secure authentication.

The lab focuses on real-world DevOps practices and is suitable for learning or production-style setups.

---

## 🎥 Video Tutorial

[![Deploy Redmine on AWS EC2 with Google OAuth](https://img.youtube.com/vi/qNP0qdtqc4g/0.jpg)](https://youtu.be/qNP0qdtqc4g)

👉 Watch on YouTube  
https://youtu.be/qNP0qdtqc4g

---

## ✨ What You’ll Learn

- Deploy Redmine on Linux using Docker
- Run Redmine on an AWS EC2 instance
- Configure Google OAuth 2.0 authentication
- Create and use OAuth Client ID & Client Secret
- Enable Google SSO login in Redmine
- Verify the complete authentication flow

---

## 📦 Resources

- **Main DevOps Labs Repository**  
  https://github.com/The-Quick-Desk/tqd-devopslabs.git

- 🔔 **Subscribe for more DevOps content**  
  https://www.youtube.com/@TQDLite  
  https://www.youtube.com/@thequickdesk25

---

## 🚀 Getting Started

### Prerequisites

- Docker
- Docker Compose

📄 Installation guide:  
https://github.com/The-Quick-Desk/thequickdesk-dev/blob/master/tutorial/blogs/docker-installation.md

---

### Usage

1. **Clone the repository**

```bash
git clone https://github.com/The-Quick-Desk/tqd-devopslabs.git
cd tqd-devopslabs/agile/redmine
````

⚠️ **Important:**
Update the environment variables in:

* `.env`
* `docker-compose.yaml`

according to your setup (ports, credentials, domain/IP).

---

2. **Start the Redmine stack**

```bash
docker-compose up -d
```

---

3. **Access Redmine**

```text
http://localhost:80

OR

http://<public-or-private-ip>:<host-port>
```

---


## 🔐 Important Configuration Notes

- Editing the `.env` file is **mandatory**.  
  Ensure you correctly configure:
  - Redmine database name, user, and password
  - PostgreSQL credentials and database settings  
  Redmine will **not start or function correctly** if these values are incorrect.

- Pay close attention to the **Redmine service port mapping** in `docker-compose.yaml`.  
  Exposing Redmine directly on a public port is **not recommended** for production.

- It is strongly advised to place Redmine **behind a secure endpoint**, such as:
  - Reverse proxy (Nginx / Traefik / Caddy)
  - HTTPS with TLS certificates
  - Controlled access via firewall or security groups

- For simplicity, this lab exposes Redmine directly, but this is intended **only for learning and DevOps labs**.

👉 If you want me to create a **reverse proxy setup (Nginx / Traefik) or HTTPS-based secure access**, leave a comment on the YouTube video and I’ll cover it in a follow-up lab.
