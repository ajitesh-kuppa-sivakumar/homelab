# 🏠 Homelab Docker Stacks

[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://docker.com)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com)

A collection of self-hosted services running in Docker containers for a complete homelab setup. This repository contains Docker Compose configurations for various applications including media management, password management, VPN services, and more.

## 📋 Table of Contents

- [🚀 Quick Start](#-quick-start)
- [📦 Available Stacks](#-available-stacks)
  - [📸 Immich - Photo Management](#-immich---photo-management)
  - [🎬 Multimedia Stack](#-multimedia-stack)
  - [🔒 Mysterium VPN](#-mysterium-vpn)
  - [💻 Termix Terminal](#-termix-terminal)
  - [🔐 Vaultwarden](#-vaultwarden)
- [⚙️ Prerequisites](#️-prerequisites)
- [🔧 Installation](#-installation)
- [📖 Usage](#-usage)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)

## 🚀 Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/homelab.git
   cd homelab
   ```

2. **Choose your stack** and navigate to its directory
   ```bash
   cd docker-stacks/immich  # or multimedia, etc.
   ```

3. **Configure environment variables**
   ```bash
   cp .env.example .env
   # Edit .env with your settings
   ```

4. **Start the services**
   ```bash
   docker compose up -d
   ```

## 📦 Available Stacks

| Stack | Description | Port | Status |
|-------|-------------|------|--------|
| [📸 Immich](#-immich---photo-management) | Photo/Video Management | 2283 | 🟢 Active |
| [🎬 Multimedia](#-multimedia-stack) | Complete Media Server | Multiple | 🟢 Active |
| [🔒 Mysterium](#-mysterium-vpn) | Decentralized VPN Node | 4449 | 🟢 Active |
| [💻 Termix](#-termix-terminal) | Web Terminal | 8080 | 🟢 Active |
| [🔐 Vaultwarden](#-vaultwarden) | Password Manager | 9080 | 🟢 Active |

### 📸 Immich - Photo Management

[![Immich](https://img.shields.io/badge/Immich-000000?style=flat&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTEyIDJDMTMuMSAyIDE0IDIuOSAxNCA0VjE2QzE0IDE3LjEgMTMuMSAxOCA5IDE4QzQuOSAxOCA0IDE3LjEgNCAxNlY0QzQgMi45IDQuOSAyIDYgMkgxOEMxOS4xIDIgMjAgMi45IDIwIDRWMTZDMjAgMTcuMSAxOS4xIDE4IDE1IDE4QzEwLjkgMTggMTAgMTcuMSAxMCAxNlY0QzEwIDIuOSA5LjEgMiA4IDJIMTJaIiBmaWxsPSIjZmZmZmZmIi8+Cjwvc3ZnPg==)](https://immich.app)

A self-hosted photo and video management solution that provides a mobile app for automatic backup, a web interface for viewing and managing media, and machine learning-powered search capabilities.

**Features:**
- 📱 Mobile app for automatic photo backup
- 🧠 Machine learning-powered search and object detection
- 🌐 Web interface for media management
- 📂 Automatic organization and tagging
- 🔒 Secure self-hosted solution

**Default Ports:**
- Web UI: `2283`

**Setup:**
```bash
cd docker-stacks/immich
cp .env.example .env
# Edit .env with your paths and database password
docker compose up -d
```

**Access:** http://localhost:2283

### 🎬 Multimedia Stack

[![Jellyfin](https://img.shields.io/badge/Jellyfin-00A4DC?style=flat&logo=jellyfin&logoColor=white)](https://jellyfin.org)
[![qBittorrent](https://img.shields.io/badge/qBittorrent-2F669E?style=flat&logo=qbittorrent&logoColor=white)](https://www.qbittorrent.org)
[![Radarr](https://img.shields.io/badge/Radarr-FFCB2B?style=flat&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHJlY3Qgd2lkdGg9IjI0IiBoZWlnaHQ9IjI0IiByeD0iNCIgZmlsbD0iI0ZGQ0IyQi8+Cjx0ZXh0IHg9IjEyIiB5PSIxNiIgdGV4dC1hbmNob3I9Im1pZGRsZSIgZmlsbD0iIzAwMCIgZm9udC1zaXplPSIxNiIgZm9udC13ZWlnaHQ9ImJvbGQiPk0iPC90ZXh0Pgo8L3N2Zz4=)](https://radarr.video)
[![Sonarr](https://img.shields.io/badge/Sonarr-5BAF5B?style=flat&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHJlY3Qgd2lkdGg9IjI0IiBoZWlnaHQ9IjI0IiByeD0iNCIgZmlsbD0iIzVCQUY1QiIvPgo8L3N2Zz4=)](https://sonarr.tv)

A comprehensive media management and streaming stack including torrenting, automated downloading, media organization, and streaming capabilities.

**Components:**
- 🛡️ **Gluetun**: VPN gateway for secure connections
- ⬇️ **qBittorrent**: Torrent client with VueTorrent UI
- 🔍 **Prowlarr**: Indexer manager for torrent sources
- 🎥 **Radarr**: Movie collection manager
- 📺 **Sonarr**: TV show collection manager
- 💬 **Bazarr**: Subtitle management
- 🎯 **Jellyseerr**: Media request management
- 📺 **Jellyfin**: Media server with hardware acceleration

**Default Ports:**
- Jellyfin: `8096` (HTTP), `8920` (HTTPS)
- qBittorrent: `8080` (via VPN)
- Radarr: `7878`
- Sonarr: `8989`
- Bazarr: `6767`
- Jellyseerr: `5055`
- Prowlarr: `9696`
- Flaresolverr: `8191`
- Gluetun: `7080`

**Setup:**
```bash
cd docker-stacks/multimedia
cp .env.example .env
# Configure VPN credentials, paths, and ports
docker compose up -d
```

**Access:**
- Jellyfin: http://localhost:8096
- Radarr: http://localhost:7878
- Sonarr: http://localhost:8989

### 🔒 Mysterium VPN

[![Mysterium](https://img.shields.io/badge/Mysterium-00D4AA?style=flat&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTEyIDJDMTMuMSAyIDE0IDIuOSAxNCA0VjE2QzE0IDE3LjEgMTMuMSAxOCA5IDE4QzQuOSAxOCA0IDE3LjEgNCAxNlY0QzQgMi45IDQuOSAyIDYgMkgxOEMxOS4xIDIgMjAgMi45IDIwIDRWMTZDMjAgMTcuMSAxOS4xIDE4IDE1IDE4QzEwLjkgMTggMTAgMTcuMSAxMCAxNlY0QzEwIDIuOSA5LjEgMiA4IDJIMTJaIiBmaWxsPSIjMDBENEFBIi8+Cjwvc3ZnPg==)](https://mystnodes.com)

A decentralized VPN node that allows you to earn cryptocurrency by providing VPN services to other users on the Mysterium Network.

**Features:**
- 🌐 Decentralized VPN infrastructure
- 💰 Earn MYST tokens by providing bandwidth
- 🔒 Secure peer-to-peer connections
- 🚀 Easy setup and management

**Default Ports:**
- Node API: `4449`

**Setup:**
```bash
cd docker-stacks/mysterium
docker compose up -d
```

**Access:** http://localhost:4449

### 💻 Termix Terminal

[![Termix](https://img.shields.io/badge/Termix-000000?style=flat&logo=terminal&logoColor=white)](https://github.com/lukegus/termix)

A web-based terminal multiplexer that provides a modern web interface for command-line operations.

**Features:**
- 🌐 Web-based terminal access
- 📱 Responsive design
- 🔧 Multiple terminal sessions
- 💾 Persistent sessions

**Default Ports:**
- Web UI: `8080`

**Setup:**
```bash
cd docker-stacks/termix
docker compose up -d
```

**Access:** http://localhost:8080

### 🔐 Vaultwarden

[![Vaultwarden](https://img.shields.io/badge/Vaultwarden-175DDC?style=flat&logo=bitwarden&logoColor=white)](https://github.com/dani-garcia/vaultwarden)

An unofficial Bitwarden-compatible server written in Rust, perfect for self-hosted password management.

**Features:**
- 🔒 Compatible with Bitwarden clients
- 🚀 Fast and lightweight
- 🔑 Secure password storage
- 📱 Mobile app support
- 🌐 Web vault interface

**Default Ports:**
- Web UI: `9080`

**Setup:**
```bash
cd docker-stacks/vaultwarden
cp .env.example .env
# Configure data path
docker compose up -d
```

**Access:** http://localhost:9080

## ⚙️ Prerequisites

- 🐳 **Docker** and **Docker Compose** installed
- 💾 Sufficient storage space for your data
- 🔑 VPN credentials (for multimedia stack)
- 👤 User permissions for Docker

## 🔧 Installation

1. **Install Docker and Docker Compose:**
   ```bash
   # Ubuntu/Debian
   sudo apt update
   sudo apt install docker.io docker-compose-v2

   # macOS with Homebrew
   brew install docker docker-compose
   ```

2. **Clone and setup:**
   ```bash
   git clone https://github.com/your-username/homelab.git
   cd homelab/docker-stacks
   ```

3. **Configure each stack** by copying and editing `.env` files

4. **Start services:**
   ```bash
   docker compose up -d
   ```

## 📖 Usage

- **Monitoring:** Use `docker ps` to check running containers
- **Logs:** View logs with `docker compose logs -f [service]`
- **Updates:** Pull latest images with `docker compose pull`
- **Backup:** Regularly backup your data volumes

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

⭐ **Star this repo** if you find it useful!