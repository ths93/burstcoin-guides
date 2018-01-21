The Burst Reference Software can be run with Docker and Docker-Compose. Since Docker supports all major platforms, this can be an easy-to-setup alternative to a platform-dependent installation of the Burst Reference Software.

## Prerequisites

- [Docker CE](https://docs.docker.com/engine/installation/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Database

Currently, Docker images for BRS version 1.3.6cg with MariaDB or H2 Database are available at [Docker Hub](https://hub.docker.com/r/burstcoin/core/tags/). You have to choose one of them, which is used to store the blockchain. We recommend MariaDB as database for the Burst Reference Software.

### MariaDB

The following `docker-compose.yml` file can be used to run BRS with MariaDB database as containers.

```
version: '3'

services:
  burstcoin:
    image: burstcoin/core:1.3.6cg-mariadb
    restart: always
    depends_on:
     - mariadb
    ports:
     - 8123:8123
     - 8125:8125
  mariadb:
    image: mariadb:10
    environment:
     - MYSQL_ROOT_PASSWORD=burstwallet
     - MYSQL_DATABASE=burstwallet
    volumes:
     - ./burst_db:/var/lib/mysql
```

Save the file and run it.

```
docker-compose up -d
```

With the `-d` flag, both containers are started as background processes. A `burst_db` folder will be created in the directory of the `docker-compose.yml` file, if it was not created before. This folder contains the MariaDB storage and the `burstwallet` database which contains the blockchain. The containers can be stopped and removed at any time via `docker-compose down`. With the next start, the `burst_db` folder will be mounted again and your previous blockchain status will be loaded.

### H2
