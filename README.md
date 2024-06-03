# self-hosted_docker_setups
A collection of my docker-compose files used to setup self-hosted services on Raspberry Pi 4

---

## List of services hosted (linked to their respective GitHub repositories)

* [AdGuard-Home](https://github.com/AdguardTeam/AdGuardHome)
* [Authelia](https://github.com/authelia/authelia)
* [Bazarr](https://github.com/linuxserver/docker-bazarr)
* [Calibre-web](https://github.com/janeczku/calibre-web)
* [Cloudflare-DDNS](https://github.com/oznu/docker-cloudflare-ddns)
* [Code-Server](https://github.com/linuxserver/docker-code-server)
* [Dockprom](https://github.com/stefanprodan/dockprom) (Prometheus + Grafana + cAdvisor + Nodeexporter + Alertmanager + Pushgateway + Caddy)
* [Duplicati](https://github.com/linuxserver/docker-duplicati)
* [Flood](https://github.com/jesec/flood)
* [Gitea](https://github.com/go-gitea/gitea) (Server + Database)
* [Gotify](https://github.com/gotify)
* [Grocy](https://github.com/linuxserver/docker-grocy)
* [Guacamole](https://hub.docker.com/r/guacamole/guacamole)
* [Home Assistant](https://github.com/linuxserver/docker-homeassistant)
* [Immich](https://github.com/immich-app/immich) (Server + ML container + Redis + Database)
* [Homer](https://github.com/bastienwirtz/homer)
* [Joplin](https://github.com/flosoft/docker-joplin-server) (Server + Database)
* [Lidarr](https://github.com/linuxserver/docker-lidarr)
* [Mealie](https://github.com/hay-kot/mealie)
* [Nextcloud](https://github.com/nextcloud/docker) (WebApp + Database + Redis + Cron)
* [Nginx Proxy Manager](https://github.com/jc21/nginx-proxy-manager) (WebApp + Database)
* [Overseerr](https://github.com/sct/overseerr)
* [Paperless-ng](https://github.com/jonaswinkler/paperless-ng) (WebServer + Redis + Gotenberg + Tika)
* [PhotoPrism](https://github.com/photoprism/photoprism) (Server + Database)
* [Plex](https://github.com/linuxserver/docker-plex)
* [PodGrab](https://github.com/akhilrex/podgrab)
* [Portainer](https://documentation.portainer.io/v2.0/deploy/ceinstalldocker/)
* [Prowlarr](https://github.com/linuxserver/docker-prowlarr)
* [qBittorrent](https://github.com/linuxserver/docker-qbittorrent)
* [Radarr](https://github.com/linuxserver/docker-radarr)
* [Readarr](https://github.com/linuxserver/docker-readarr)
* [Snapdrop](https://github.com/RobinLinus/snapdrop)
* [Sonarr](https://github.com/linuxserver/docker-sonarr)
* [SurfShark VPN](https://github.com/ilteoood/docker-surfshark)
* [Traggo](https://github.com/traggo/server)
* [Transmission](https://github.com/linuxserver/docker-transmission)
* [Tube-Archivist](https://github.com/bbilly1/tubearchivist) (Frontend + ElasticSearch + RedisJSON)
* [Uptime-Kuma](https://github.com/louislam/uptime-kuma)
* [Vaultwarden](https://github.com/dani-garcia/vaultwarden)
* [Vikunja](https://github.com/go-vikunja) (Frontend + API + Database + Redis + Proxy)
* [Wallabag](https://github.com/wallabag/wallabag) (WebApp + Database + Redis)
* [Watchtower](https://github.com/containrrr/watchtower)
* [Wireguard](https://github.com/linuxserver/docker-wireguard)
* [Wordpress](https://hub.docker.com/_/wordpress) (WebServer + Database)

Discover other awesome self-hosted services at - https://github.com/awesome-selfhosted/awesome-selfhosted

---
## Getting started
Install ```docker``` and ```docker-compose``` on your RPi to start building containers

### Update and Upgrade
``` bash
sudo apt-get update && sudo apt-get upgrade
```

### Install docker
``` bash
curl -sSL https://get.docker.com | sh
```

### Add a Non-Root User to the Docker group
``` bash
# Add users to the Docker group (ex. pi)
sudo usermod -aG docker pi

# Add permissions for the current user
sudo usermod -aG docker ${USER}

# Check 
groups ${USER}
```

### Install Docker-Compose
``` bash
sudo apt-get install docker-compose plugin
```

### Enable Docker to start your containers on boot
``` bash
sudo systemctl enable docker
```

### Test Docker with a ```hello-world``` container
``` bash
docker run hello-world
```

### Start a container using docker-compose
Navigate to project root directory which contains the ```docker-compose.yml``` file
``` bash
docker compose up -d
```

### Upgrading containers with Docker-Compose
``` bash
# Pull the latest images
docker compose pull

# Stop running containers
docker compose stop

# Remove stopped containers
docker compose rm -f

# Rebuild containers with updated images
docker compose up -d --build
```
