FROM ubuntu:16.04


RUN apt-get update -y && \
    apt-get install -y \
    apt-transport-https ca-certificates gnupg software-properties-common wget build-essential

RUN apt-add-repository 'deb https://apt.kitware.com/ubuntu/ xenial main' && \
    apt-get update -y

RUN apt-get install -y --allow-unauthenticated cmake
