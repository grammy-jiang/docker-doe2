# Docker for DOE2

This repository provides the dockerfile for DOE2 and a docker-compose to build
the image.

## Create the image

### Create the image from dockerfile directly

Run command:
```bash
docker build --tag doe22:s48zr52n --file versions/ubuntu/dockerfile --build-arg DOE22PASSWORD=password .
```

### Creata the image from docker-compose

Run command:
```bash
docker-compose build
```

## Run the simulation

Run command:
```bash
docker run -it \
    --rm \
    --volume "/home/grammy-jiang/PycharmProjects/docker-doe2/simple:/root/.wine/drive_c/simple" \
    doe22:s48zr52n \
    wineconsole cmd /c c:/doe22/doe22 exe48z c:/simple/simple chicagil
```
