FROM debian:bookworm

RUN dpkg --add-architecture arm64 && \
    apt-get update && \
    apt-get full-upgrade --no-install-recommends -y \
        build-essential crossbuild-essential-arm64 default-jdk-headless git \
        cmake debhelper devscripts lintian swig pkgconf:arm64 python3-dev:arm64 \
        libjson-c-dev:arm64 libstdc++6:arm64 && \
    adduser --gecos runner --disabled-password runner && \
    rm -rf /var/lib/apt/lists/*
