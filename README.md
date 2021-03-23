# Docker Plex

Fork of https://github.com/linuxserver/docker-plex with [mauimauer](https://github.com/mauimauer) 's fixes for HW decoding with **AMD APUs** 

## Usage

Here are some example snippets to help you get started creating a container.

### docker-compose ([recommended](https://docs.linuxserver.io/general/docker-compose))

Compatible with docker-compose v2 schemas.

```yaml
---
version: "2.1"
services:
  plex:
    image: ghcr.io/linuxserver/plex
    container_name: plex
    network_mode: host
    environment:
      - PUID=1000
      - PGID=1000
      - VERSION=docker
      - PLEX_CLAIM= #optional
    volumes:
      - /path/to/library:/config
      - /path/to/tvseries:/tv
      - /path/to/movies:/movies
    restart: unless-stopped
```

### docker cli

```
docker run -d \
  --name=plex \
  --net=host \
  -e PUID=1000 \
  -e PGID=1000 \
  -e VERSION=docker \
  -e PLEX_CLAIM= `#optional` \
  -v /path/to/library:/config \
  -v /path/to/tvseries:/tv \
  -v /path/to/movies:/movies \
  --restart unless-stopped \
  ghcr.io/linuxserver/plex
```

For detailed info about parameters go to https://github.com/linuxserver/docker-plex#parameters 