# Caddy

项目简介
---
本项目使用Github Action对Caddy进行编译并打包Docker镜像

#### 插件:
 - github.com/caddyserver/cache-handler
 - github.com/ueffel/caddy-brotli
 - github.com/caddyserver/transform-encoder
 - github.com/RussellLuo/caddy-ext/ratelimit
 - github.com/caddy-dns/cloudflare

安装
---

- ## Docker

    ### Docker-CLI

        ```
        #Debian-slim底包
        docker run -p 80:80 -p 443:443 -v ./caddy/config:/data/caddy/config -v ./caddy/config.d:/data/caddy/config.d -v ./caddy/log:/data/caddy/log --restart always wjqserver/caddy:latest
        #Alpine底包
        docker run -p 80:80 -p 443:443 -v ./caddy/config:/data/caddy/config -v ./caddy/config.d:/data/caddy/config.d -v ./caddy/log:/data/caddy/log --restart always wjqserver/caddy:alpine
        ```

    ### Docker-Compose

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
