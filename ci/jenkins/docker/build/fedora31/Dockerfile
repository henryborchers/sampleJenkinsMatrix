FROM fedora:31

RUN dnf update -y && \
    dnf group install "C Development Tools and Libraries" -y && \
    dnf install -y cmake &&
    dnf install -y git
