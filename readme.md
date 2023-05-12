# docker-bitcoin

[![Build]][build_url]
[![Version]][tag_url]
[![Size]][tag_url]
[![Pulls]][hub_url]

A docker image of Bitcoin Core with support for the following platforms:

* `amd64` (x86_64)
* `arm32v7` (armv7)
* `arm64` (aarch64, armv8)

## Usage

Via `docker-compose.yml`

```yaml
version: "3"
services:
  bitcoin:
    container_name: bitcoin
    image: kroese/docker-bitcoin:latest
    ports:
      - 8332:8332
      - 8333:8333
    volumes:
      - /opt/bitcoin:/home/bitcoin/.bitcoin
    restart: on-failure
```

Via `docker run`

```bash
docker run -it --rm kroese/docker-bitcoin:latest -printtoconsole
```

Executing `getinfo` on a running container:

```bash
docker exec --user bitcoin bitcoin bitcoin-cli -getinfo
```

[build_url]: https://github.com/kroese/docker-bitcoin/
[hub_url]: https://hub.docker.com/r/kroese/docker-bitcoin
[tag_url]: https://hub.docker.com/r/kroese/docker-bitcoin/tags

[Build]: https://github.com/kroese/docker-bitcoin/actions/workflows/build.yml/badge.svg
[Size]: https://img.shields.io/docker/image-size/kroese/docker-bitcoin/latest?color=066da5&label=size
[Pulls]: https://img.shields.io/docker/pulls/kroese/docker-bitcoin.svg?style=flat&label=pulls&logo=docker
[Version]: https://img.shields.io/docker/v/kroese/docker-bitcoin?arch=amd64&sort=semver&color=066da5
