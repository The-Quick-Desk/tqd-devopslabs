# 🎬 Jellyfin Media Server Stack (Jellyfin + Radarr + Prowlarr + qBittorrent)

This repository accompanies the video tutorial where I deploy a **self-hosted media server stack** using:

* **Jellyfin** → media streaming
* **Radarr** → movie management
* **Prowlarr** → indexer management
* **qBittorrent** → download client

All deployed using **Docker Compose** on a Linux server.

---

## 🎥 Video Tutorial

👉 **Watch on YouTube**
[Build Your Own Netflix at Home 🔥 Jellyfin + Radarr + Docker (Complete Media Server Guide)](https://youtu.be/Gfd2oJAdaIk)

---

## ✨ Key Takeaways

* Deploying a complete **self-hosted media stack**
* Understanding **container volume mapping (critical for Radarr/qBittorrent)**
* Automating media workflows:

  * Search → Download → Organize → Stream
* Building your own **Netflix-like system**

---

## 📦 Resources

* **Main DevOps Labs Repository**
  [https://github.com/The-Quick-Desk/tqd-devopslabs.git](https://github.com/The-Quick-Desk/tqd-devopslabs.git)

* **Media Stack Folder**
  `tqd-devopslabs/media/jrpq`

* 🔔 **Subscribe for more DevOps content**
  [https://www.youtube.com/@TQDLite](https://www.youtube.com/@TQDLite)
  [https://www.youtube.com/@thequickdesk25](https://www.youtube.com/@thequickdesk25)

---

## 🚀 Getting Started

### Prerequisites

* Docker
* Docker Compose
* Git

[Installation Document - Docker, Git & Docker Compose](https://github.com/The-Quick-Desk/thequickdesk-dev/blob/master/tutorial/blogs/docker-installation.md)
### Usage

---

## ⚙️ Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/The-Quick-Desk/tqd-devopslabs.git
cd tqd-devopslabs/media/jrpq
```

---

### 2. Create required directories

```bash
mkdir -p /data/media/movies
mkdir -p /data/media/tv
mkdir -p /data/torrents/{complete,incomplete}
```

📌 Final structure:

```bash
/data
 ├── media
 │   ├── movies
 │   └── tv
 └── torrents
     ├── complete
     └── incomplete
```

---

### 3. Start the stack

```bash
docker-compose up -d
```

---

## 🌐 Access Services

| Service     | URL              |
| ----------- | ---------------- |
| Jellyfin    | `http://IP:8096` |
| Radarr      | `http://IP:7878` |
| Prowlarr    | `http://IP:9696` |
| qBittorrent | `http://IP:8080` |

👉 Replace `IP` with:

* Public IP (EC2 / cloud)
* Private IP (local network)

---

## ⚠️ Important Configuration Notes

### 🔴 Critical: Volume Mapping

All services use:

```bash
/data
```

This ensures:

* Radarr can see downloads from qBittorrent
* No “path does not exist” errors
* Hardlinks work correctly

---

### 📥 qBittorrent Settings

Set download paths:

```
/data/torrents/complete
/data/torrents/incomplete
```

---

### 🎬 Radarr / Sonarr Root Folders

```
/data/media/movies
/data/media/tv
```

---

### 🔗 Workflow

```
Radarr
      ↓
Prowlarr (search)
      ↓
qBittorrent (download)
      ↓
/data/torrents/complete
      ↓
Radarr import
      ↓
/data/media
      ↓
Jellyfin streams
```

---

## 🔐 Networking / Ports

Make sure to allow the required ports:

* 8096 → Jellyfin
* 7878 → Radarr
* 9696 → Prowlarr
* 8080 → qBittorrent

For cloud (AWS EC2):

* Update **Security Group inbound rules**

---

## ⚠️ Disclaimer

This project is intended for educational and self-hosting learning purposes only.

The tools demonstrated in this repository are general-purpose software. How they are used is entirely the responsibility of the user.

Please ensure that any media you access or manage is legally obtained and complies with your local laws.

I do not promote, support, or encourage piracy or unauthorized distribution of copyrighted content.

---

## 🧠 Notes

* This setup focuses on **infrastructure and automation**, not content
* Works best on:

  * Home server
  * VPS
  * AWS EC2 (with storage considerations)

---

## 🚀 Future Improvements

* Reverse proxy (Traefik / Nginx)
* HTTPS + domain setup
* Overseerr (media request UI)
* GPU transcoding for Jellyfin
