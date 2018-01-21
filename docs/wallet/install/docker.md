The Burst Reference Software can be run with Docker and Docker-Compose. Since Docker supports all major platforms, this can be an easy-to-setup alternative to a platform-dependent installation of the Burst Reference Software.

## Prerequisites

- [Docker CE](https://docs.docker.com/engine/installation/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Database

Currently, Docker images for BRS version 1.3.6cg with MariaDB or H2 Database are available at [Docker Hub](https://hub.docker.com/r/burstcoin/core/tags/). You have to choose one of them, which is used to store the blockchain. We recommend MariaDB as database for the Burst Reference Software.

### MariaDB

The following `docker-compose.yml` file can be used to run the BRS with MariaDB database in containers.

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

With the `-d` flag, both containers are started as background processes. A `burst_db` folder will be created in the directory of the `docker-compose.yml` file, if it was not created before. This folder is mounted to the MariaDB storage and holds the `burstwallet` database containing the blockchain. The containers can be stopped and removed at any time via `docker-compose down`. With the next start, the `burst_db` folder will be mounted again and your previous blockchain status will be loaded.

!!! important
    You may encounter an PoolInitializationError when not clearing containers on restart of the docker-compose.yml. In case there are old containers, remove them with `docker rm $(docker ps -a -q)`

### H2

Alternatively, H2 can be used as database to store the blockchain. H2 is an embedded database, therefore one does not have to run it in a separate container. Simply run the following command.

```
docker run -p 8123:8123 -p 8125:8125 -v "$(pwd)"/burst_db:/etc/burstcoin/burst_db -d burstcoin/core:1.3.6cg-h2
```

`"$(pwd)"/burst_db` is the path to the folder which is mounted to the H2 storage. If it does not exist a new `burst_db` folder is created in the current directory.

!!! abstract "Source"
    The Dockerfiles used to create the Docker images can be found on [Github - https://github.com/PoC-Consortium/burstcoin-docker](https://github.com/PoC-Consortium/burstcoin-docker)

## Custom configuration

In order to use a custom config - `nxt.properties` file, you can simply mount a folder containing the `nxt-default.properties` and the `nxt.properties` to the `/etc/burstcoin/conf` mount point.

**MariaDB**

``` yaml
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
    volumes:
     - ./conf:/etc/burstcoin/conf
  mariadb:
    image: mariadb:10
    environment:
     - MYSQL_ROOT_PASSWORD=burstwallet
     - MYSQL_DATABASE=burstwallet
    volumes:
     - ./burst_db:/var/lib/mysql
```

**H2**

```
docker run -p 8123:8123 -p 8125:8125 -v "$(pwd)"/burst_db:/etc/burstcoin/burst_db -v "$(pwd)"/conf:/etc/burstcoin/conf -d burstcoin/core:1.3.6cg-h2
```
