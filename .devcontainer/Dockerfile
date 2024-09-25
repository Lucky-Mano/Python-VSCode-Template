FROM python:3.12-slim

LABEL maintainer "Yukinori Manome <phatbowie@gmail.com>"

RUN apt-get update \
    && apt-get install -y \
        build-essential \
        clang \
        git \
    && pip install -U --no-cache-dir pip setuptools poetry \
    && rm -rf /var/lib/apt/lists/*

ARG UID=1000
ARG GID=1000

RUN groupadd -g ${GID} docker \
    && useradd -u ${UID} -g ${GID} -s /bin/bash -m docker

USER ${UID}

WORKDIR /app
