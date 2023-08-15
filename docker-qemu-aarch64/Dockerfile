FROM ubuntu:20.04

ARG DEBIAN_FRONTEND=noninteractive

RUN dpkg --add-architecture arm64 && { \
        echo 'deb [arch=amd64] http://archive.ubuntu.com/ubuntu/ focal main universe'; \
        echo 'deb [arch=amd64] http://archive.ubuntu.com/ubuntu/ focal-updates main universe'; \
        echo 'deb [arch=arm64] http://ports.ubuntu.com/ubuntu-ports focal main universe'; \
        echo 'deb [arch=arm64] http://ports.ubuntu.com/ubuntu-ports focal-updates main universe'; \
    } > /etc/apt/sources.list

RUN apt-get update \
    && apt-get install --no-install-recommends -y \
        clang-12:arm64=1:12.* \
        liblld-12-dev:arm64=1:12.* \
        libc6-lse:arm64=2.* \
        libgcc-s1:arm64=10.* \
        libtinfo6:arm64=6.* \
        libzstd1:arm64=1.* \
        qemu-user \
    && ln -s /usr/lib/aarch64-linux-gnu/libtinfo.so.6 /usr/lib/aarch64-linux-gnu/libtinfo.so \
    && ln -s /usr/lib/aarch64-linux-gnu/libzstd.so.1 /usr/lib/aarch64-linux-gnu/libzstd.so \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /var/cache/apt \
    :

WORKDIR /elfshaker

CMD ["echo", "See https://github.com/elfshaker/manyclangs/blob/main/docker-qemu-aarch64/README.md"]
