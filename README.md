# boilerplate-machine-learning-dockerfiles [![Build Status][travis-image]][travis-url] [![License: MIT][license-image]][license-url]

Boilerplate of Dockerfiles for Jupyter Notebook, Tensorflow, Keras and so on.

## Required

- Docker installed

## Getting started

- Clone this repo
- Select `Dockerfile` and Edit `dockerfile` value in `docker-compose.yml`
- Run `docker-compose up --build` in terminal

## Default Settings

- Port: 8888:8888
- Volume: ./data/notebooks:/data/notebooks

## Dockerfile List

| Dockerfile Name           | Main Packages                                 | Virtual Env. | Base Image            |
| ------------------------- | --------------------------------------------- | ------------ | --------------------- |
| Dockerfile.base           | Anaconda, Jupyter Notebook                    | Not used     | continuumio/anaconda3 |
| Dockerfile.tensorflow-env | Anaconda, Jupyter Notebook, Tensorflow        | Activated    | continuumio/anaconda3 |
| Dockerfile.tensorflow     | Anaconda, Jupyter Notebook, Tensorflow        | Not used     | keidrun/ml-base       |
| Dockerfile.keras          | Anaconda, Jupyter Notebook, Tensorflow, Keras | Not used     | keidrun/ml-base       |

## Docker Image List

| Docker Image Name          | Built Dockerfile Name     |
| -------------------------- | ------------------------- |
| keidrun/ml-base            | Dockerfile.base           |
| keidrun/ml-tensorflow      | Dockerfile.tensorflow     |
| keidrun/ml-keras           | Dockerfile.keras          |

For example, if you'd like to use `keidrun/ml-keras` image, run the following command:

```bash
docker container run -it -p 8888:8888 -v $(pwd)/data/notebooks:/data/notebooks keidrun/ml-keras
```

Or edit `image` value in `docker-compose.image.yml` and run the following command:

```bash
docker-compose -f docker-compose.image.yml up
```

[travis-url]: https://travis-ci.org/keidrun/boilerplate-machine-learning-dockerfiles
[travis-image]: https://secure.travis-ci.org/keidrun/boilerplate-machine-learning-dockerfiles.svg?branch=master
[license-url]: https://opensource.org/licenses/MIT
[license-image]: https://img.shields.io/badge/License-MIT-yellow.svg
