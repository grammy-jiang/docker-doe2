# Docker for DOE2

This repository provides the dockerfile for DOE2 and a docker-compose to build
the image.

## Create the image

### Create the image from dockerfile directly

Run command:
```bash
docker build \
  --build-arg DOE22PASSWORD=<password> \
  --file versions/python/dockerfile \
  --tag <your name>/doe2:<doe2 version> \
  .
```

### Creata the image from docker-compose

Run command:
```bash
docker-compose build
```

## Run the simulation

Run command:
```bash
docker run \
    -it \
    --rm \a
    --volume "/home/grammy-jiang/PycharmProjects/docker-doe2/sample:/root/.wine/drive_c/sample" \
    <your name>/doe2:<doe2 version> \
    wine cmd /c c:/doe22/doe22 exe48z c:/sample/sample chicagil
```
where:

> -it: it is necessary, even there is no interactive
>
> --volume: the path of the project, mount it to `/root/.wine/drive_c/sample` to make it available in wine
>
> wine: running the batch file with `cmd.exe`
>
> doe22: `c:/doe22/doe22` is the batch file of `doe22.bat`, `exe48z` is the version of `doe22`, `c:/simple/simple` is the path of inp file (without `inp` postfix), `chicagil` is the weather file which located in `c:/doe22/weather`
