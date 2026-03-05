# Home Server Monorepo

This repository serves as the central source of truth for my home server infrastructure. It utilizes a **monorepo** architecture to manage multiple containerized services, configurations, and automation scripts in a single location.

The infrastructure is built on **Podman** for rootless, secure container management, orchestrated via `podman-compose`.

## 📂 Project Structure

The repository is organized to separate configuration (Git-tracked) from persistent data (local-only).

** Since this is a in-dev project, the structure below is a template/desire, things can change (a lot) **

```text
home-server/
├─ .logs/                       # Logs for the homelab servers
│
├─ homelab_deploy/              # Deploy files for the homelab servers
│  ├─ scripts/                  # Specific scripts for the deploy
│  └─ templates/                # Templates for the deploy
│
├─ services/                    # Files shared between services
│  ├─ assets/                   # Assets used by multiple services
│  │   ├─ backups/              # General backups
│  │   ├─ documents/            # Managed documents
│  │   ├─ markdowns/            # Destined for all the markdown shared files
│  │   └─ workflows/            # Saved pipelines and workflows
│  │
│  ├─ media/                    # Folder destined to save all media files
│  │  ├─ 1-games/               # Game related files
│  │  │  ├─ svr_minecraft/      # Minecraft server files
│  │  │  └─ roms/               # Roms for emulators
│  │  │
│  │  ├─ 2-books/               # Stored books
│  │  ├─ 3-audiobooks/          # Stored music
│  │  ├─ 4-podcasts/            # Stored podcasts
│  │  ├─ 5-music/               # Stored music
│  │  ├─ 6-photos/              # Stored photos
│  │  ├─ 7-movies/              # Stored movies
│  │  ├─ 8-series/              # Stored series and tv shows
│  │  ├─ 9-videos/              # Stored videos
│
├─ .env
├─ .gitgnore
├─ compose.yaml
└─ README.md


```

Links for apps used in this home lab (Table of Contents)

| App | Type | About | Docker Hub |
| --- | --- | --- | --- |
| [Nginx](https://nginx.org/) | Web/DNS | Reverse Proxy | https://hub.docker.com/hardened-images/catalog/dhi/nginx |
| [DuckDNS](https://www.duckdns.org/) | Web/DNS | DNS handler (Traffic that goes in my home) | https://hub.docker.com/r/linuxserver/duckdns
| [Pi-hole](https://pi-hole.net/) | Web/DNS | DNS handler (Traffic that goes out my home) | https://hub.docker.com/r/diginc/pi-hole |
| [Tailscale](https://tailscale.com/) | Web/DNS | VPN | https://hub.docker.com/extensions/tailscale/docker-extension |
| [Chibi Safe](https://chibisafe.moe/) | Server Management | Remote file manager | https://hub.docker.com/r/chibisafe/chibisafe |
| [Duplicati](https://duplicati.com/) | Server Management | Backup | https://hub.docker.com/r/linuxserver/duplicati |
| PostgresDB | Database Tools | Database | https://hub.docker.com/_/postgres |
| Superset | Database Tools | Dashboards | https://hub.docker.com/r/apache/superset |
| [Home Assistant](https://www.home-assistant.io/) | Server Tools | Automation | https://hub.docker.com/r/home-assistant/home-assistant |
| [Next Cloud](https://nextcloud.com/) | Server Tools | Open Source office tools | https://hub.docker.com/_/nextcloud/ |
| N8N | Server Tools | Automation | https://hub.docker.com/r/n8nio/n8n |
| [Flame](https://github.com/pawelmalak/flame?ref=roadtohomelab.blog) | Server Front | Homelab homescreen | https://hub.docker.com/r/pawelmalak/flame |
| Retroarch | Media | Gamming emulation home | https://hub.docker.com/r/linuxserver/retroarch |
| Minecraft Server | Media | Gamming server | https://hub.docker.com/r/itzg/minecraft-server |
| [Plex](https://watch.plex.tv/) | Media | Media Streaming Server | https://hub.docker.com/r/linuxserver/plex |
| [Jellyfin](https://jellyfin.org/) | Media | Media Streaming Server| https://hub.docker.com/r/linuxserver/jellyfin |
| Ollama | AI | Ai agent engine | https://hub.docker.com/r/ollama/ollama |
| Open Web UI | AI | Ai agent GUI | https://docs.openwebui.com/getting-started/quick-start/ |



