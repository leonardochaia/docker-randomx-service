# Docker randomx-service

Run `randomx-service` using Docker.

This image clones `https://github.com/tevador/randomx-service/` and builds it according to instructions.

## Usage

Append any `randomx-service` params after the image name. i.e:

```shell
docker run -it --rm lchaia/randomx-service -origin https://github.com # ..
```

## Docker Compose example

```yaml
version: "3"

services:
  randomx-service:
    image: lchaia/randomx-service
    container_name: randomx-service
    build:
        context: ./src
    ports:
        - 39093:39093
    command: "-host 0.0.0.0 -log -threads 4 -origin http://localhost:4200"
```

## Donations

Please consider [donating to Tevador](https://github.com/tevador/randomx-service#donations).
