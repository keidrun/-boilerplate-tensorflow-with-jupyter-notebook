# boilerplate-machine-learning-dockerfiles-for-anaconda [![Build Status][travis-image]][travis-url] [![License: MIT][license-image]][license-url]

Boilerplate of Dockerfiles for Jupyter Notebook, Tensorflow, Keras and so on with Anaconda.

## Required

- Docker installed

## Getting started

- Clone this repo
- Select `Dockerfile` and Edit `dockerfile` value in `docker-compose.yml`
- Run `docker-compose up --build` in terminal

## Default Settings

- Port: `8888:8888`
- Volume: `./data:/data`
- --notebook-dir: `/data/notebooks`

## Dockerfile List

| Dockerfile Name            | Main Packages                                  | Virtual Env. | Base Image             |
| -------------------------- | ---------------------------------------------- | ------------ | ---------------------- |
| Dockerfile.tensorflow-env  | Anaconda, Jupyter Notebook, Tensorflow         | Activated    | continuumio/anaconda3  |
| Dockerfile.ana.base        | Anaconda, Jupyter Notebook                     | Not used     | continuumio/anaconda3  |
| Dockerfile.ana.tensorflow  | Anaconda, Jupyter Notebook, Tensorflow         | Not used     | keidrun/ml-base        |
| Dockerfile.ana.keras       | Anaconda, Jupyter Notebook, Tensorflow, Keras  | Not used     | keidrun/ml-base        |
| Dockerfile.ana.pytorch     | Anaconda, Jupyter Notebook, Pytorch            | Not used     | keidrun/ml-base        |å

## Docker Image List

| Docker Image Name          | Built Dockerfile Name      |
| -------------------------- | -------------------------- |
| [keidrun/ml-base](https://hub.docker.com/r/keidrun/ml-base/)            | Dockerfile.ana.base        |
| [keidrun/ml-tensorflow](https://hub.docker.com/r/keidrun/ml-tensorflow/)      | Dockerfile.ana.tensorflow  |
| [keidrun/ml-keras](https://hub.docker.com/r/keidrun/ml-keras/)           | Dockerfile.ana.keras (outdated) |
| [keidrun/ml-pytorch](https://hub.docker.com/r/keidrun/ml-pytorch/)           | Dockerfile.ana.pytorch     |

NOTE: Tensorflow 2.0 supports Keras so use an above tensorflow image if you'd like a keras image.

For example, if you'd like to use `keidrun/ml-keras` image, run the following command:

```bash
docker container run -it -p 8888:8888 -v $(pwd)/data:/data keidrun/ml-keras
```

Or edit `image` value in `docker-compose.image.yml` and run the following command:

```bash
docker-compose -f docker-compose.image.yml up
```

[travis-url]: https://travis-ci.org/keidrun/boilerplate-machine-learning-dockerfiles-for-anaconda
[travis-image]: https://secure.travis-ci.org/keidrun/boilerplate-machine-learning-dockerfiles-for-anaconda.svg?branch=master
[license-url]: https://opensource.org/licenses/MIT
[license-image]: https://img.shields.io/badge/License-MIT-yellow.svg
