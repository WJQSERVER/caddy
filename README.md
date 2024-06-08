# Caddy

- ### 1
- ### 2

## Docker-CLI

### Debian-slim

```
docker run -p 80:80 -p 443:443 -v ./caddy/config:/data/caddy/config -v ./caddy/config.d:/data/caddy/config.d -v ./caddy/log:/data/caddy/log --restart always wjqserver/caddy:latest
```

### Alpine

```
docker run -p 80:80 -p 443:443 -v ./caddy/config:/data/caddy/config -v ./caddy/config.d:/data/caddy/config.d -v ./caddy/log:/data/caddy/log --restart always wjqserver/caddy:alpine
```

Docker-Compose
---

```
version: '3.9'
services:
    caddy:
        image: 'wjqserver/caddy:latest'
        restart: always
        volumes:
            - './caddy/log:/data/caddy/log'
            - './caddy/config.d:/data/caddy/config.d'
            - './caddy/config:/data/caddy/config'
        ports:
            - '443:443'
            - '80:80'

```
