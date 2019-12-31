![](https://images.microbadger.com/badges/version/gists/qbittorrent.svg) ![](https://images.microbadger.com/badges/image/gists/qbittorrent.svg) ![](https://img.shields.io/docker/stars/gists/qbittorrent.svg) ![](https://img.shields.io/docker/pulls/gists/qbittorrent.svg)

#### Environment:

| Environment | Default value |
|-------------|---------------|
| PEER_PORT | 6881            |
| WEB_PORT  | 8080            |
| UID       | 1000            |
| GID       | 1000            |

#### Creating an instance:

    docker run \
        -d \
        --name qbittorrent \
        -p 6881:6881 \
        -p 6881:6881/udp \
        -p 8080:8080 \
        -v /path/data:/config
        gists/qbittorrent

Note: 

- username: admin,
- password: adminadmin

#### Compose example:

    qbittorrent:
        image: gists/qbittorrent
        ports:
            - "8080:8080"
            - "6881:6881"
            - "6881:6881/udp"
        volumes:
            - /path/data:/data
        environment:
            - UID=1000
            - GID=1000
      restart: always