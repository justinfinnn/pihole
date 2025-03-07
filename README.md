# Pi-hole Docker Setup

This repository provides a **Docker Compose** configuration for setting up **Pi-hole**, a network-wide ad blocker that functions as a DNS-level blocker for unwanted ads and trackers.

## 📌 What is Pi-hole?

[Pi-hole](https://pi-hole.net/) is a DNS filtering solution that blocks advertisements and malicious domains at the network level. It can replace your router's DNS and stop ads before they even reach your devices.

## 🛠 Services

### 🚀 Pi-hole

- **Container Name:** `pihole`
- **Image:** `pihole/pihole:latest`
- **Network Mode:** `host` (Ensures proper DNS functionality)
- **Configuration Files:**
  - `./config:/etc/pihole` → Stores Pi-hole settings.
  - `./dnsmasq.d:/etc/dnsmasq.d` → Stores DNS settings.
- **Environment Variables:** Defined in `.env` file.
- **Restart Policy:** `unless-stopped` (Auto-restarts if the container crashes)

## Environment Variables

You can pass variables directly from the docker-compose file or create a `.env` file to pull them in on build.
Would suggest including some basic ones:

```
ServerIP=[your server IP here, make sure it is static]
PIHOLE_DNS_=1.1.1.1;8.8.8.8
TZ=[your timezone]
```

## 📌 Getting Started

### 1️⃣ Prerequisites

- Ensure **Docker** and **Docker Compose** are installed. ([Guide](https://docs.docker.com/get-docker/))

### 2️⃣ Clone the Repository

```sh
git clone https://github.com/your_username/pi-hole-docker.git
cd pi-hole-docker
```
