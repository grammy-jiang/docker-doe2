# Docker for DOE2

This repository provides the dockerfile for DOE2 and a docker-compose to build
the image.

## Create the image from dockerfile directly

Run command:
```bash
docker build --tag doe22:s48zr52n --file versions/ubuntu/dockerfile --build-arg DOE22PASSWORD=password .
```

## Creata the image from docker-compose

Run command:
```bash
docker-compose build
```
