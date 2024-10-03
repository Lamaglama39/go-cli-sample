# syntax=docker/dockerfile:1
FROM golang:1.21-bullseye

ARG USERNAME=user

RUN apt-get update -y \
    && DEBIAN_FRONTEND=noninteractive \
    apt-get install -y --no-install-recommends \
    git \
    locales \
    tzdata \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN locale-gen ja_JP.UTF-8 \
    && localedef -f UTF-8 -i ja_JP ja_JP.UTF-8
ENV TZ=Asia/Tokyo \
    LANG=ja_JP.UTF-8 \
    LANGUAGE=ja_JP:jp \
    LC_ALL=ja_JP.UTF-8

RUN groupadd -r $USERNAME && useradd -r -g $USERNAME $USERNAME
RUN mkdir /home/$USERNAME
USER $USERNAME

WORKDIR /workspaces
