# Home Server Monorepo

This repository serves as the central source of truth for my home server infrastructure. It utilizes a **monorepo** architecture to manage multiple containerized services, configurations, and automation scripts in a single location.

The infrastructure is built on **Podman** for rootless, secure container management, orchestrated via `podman-compose`.

## 📂 Project Structure

The repository is organized to separate configuration (Git-tracked) from persistent data (local-only).

** Since this is a in-dev project, the structure below is a template/desire, things can change (a lot) **

```text
home-server/
├── compose.yaml             # Master orchestration file for all services
├── .env.example             # Template for environment variables
├── services/                # Isolated configuration for each service
│   │
│   ├── [custom-service]/    # Example: Custom notepad map (This can be a MCP, a API, a portal...)
│   │   ├── config/          # Map to /config inside of the docker
│   │   ├── data/            # Can maped to /data, loke a volume
│   │   ├── src/             # Service-specific scripts and logic
│   │   └── Dockerfile       # If a custom service is developed, store the dockerfile here
│   │
│   ├── [home-page]/         # Service that create a home page for your home-lab
│   │   ├── config/          # Map to /config inside of the docker
│   │   └── dnsmasq.d/       # Maps to /etc/dnsmasq.d. Stores advanced network routing rules.
│   │
│   ├── [example-pi-hole]/   # Example of a service that is not custom, just a container
│   │   ├── etc-pihole/      # Maps to /etc/pihole inside the container. Stores your blocklists and custom DNS records.
│   │   └── dnsmasq.d/       # Maps to /etc/dnsmasq.d. Stores advanced network routing rules.
│   │
│   ├── [service-name]/      # e.g., media-server, dns, proxy
│   │   ├── config/          # Service-specific config files
│   │   └── Dockerfile       # (Optional) Custom build definition
│   │
├── data/                    # Persistent data volumes (ignored by Git)
└── scripts/                 # Helper scripts (backup, deploy, maintenance)
```

Links for apps used in this home lab (Table of Contents)

| App | About | Docker Hub |
| --- | --- | --- |
| [Nginx](https://nginx.org/) | Reverse Proxy | https://hub.docker.com/hardened-images/catalog/dhi/nginx |
| [DuckDNS](https://www.duckdns.org/) | DNS handler (Traffic that goes in my home) | https://hub.docker.com/r/linuxserver/duckdns
| [Pi-hole](https://pi-hole.net/) | DNS handler (Traffic that goes out my home) | https://hub.docker.com/r/diginc/pi-hole |
| [Tailscale](https://tailscale.com/) | VPN | https://hub.docker.com/extensions/tailscale/docker-extension |
| [Chibi Safe](https://chibisafe.moe/) | Remote file manager | https://hub.docker.com/r/chibisafe/chibisafe |
| [Duplicati](https://duplicati.com/) | Backup | https://hub.docker.com/r/linuxserver/duplicati |
| [Flame](https://github.com/pawelmalak/flame?ref=roadtohomelab.blog) | Homelab homescreen | https://hub.docker.com/r/pawelmalak/flame |
| PostgresDB | Database | https://hub.docker.com/_/postgres |
| Superset | Dashboards | https://hub.docker.com/r/apache/superset |
| N8N | Automation | https://hub.docker.com/r/n8nio/n8n |
| Ollama | LLM engine | https://hub.docker.com/r/ollama/ollama |
| Open Web UI | LLM GUI | https://docs.openwebui.com/getting-started/quick-start/ |
| [Plex](https://watch.plex.tv/) | Media Server | https://hub.docker.com/r/linuxserver/plex |



https://github.com/Haxxnet/Compose-Examples?tab=readme-ov-file#backups




| Jellyfin | https://jellyfin.org/ | https://hub.docker.com/r/linuxserver/jellyfin |
| Pi-hole | https://pi-hole.net/ | https://hub.docker.com/r/pihole/pihole |
| Home Assistant | https://www.home-assistant.io/ | https://hub.docker.com/r/home-assistant/home-assistant |
| Nextcloud | https://nextcloud.com/ |
| Plex | https://www.plex.tv/ |
| Synology | https://www.synology.com/ |
| QNAP | https://www.qnap.com/ |
| Synology | https://www.synology.com/ |
| Synology | https://www.synology.com/ |


