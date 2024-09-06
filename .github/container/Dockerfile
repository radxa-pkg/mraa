FROM debian:bookworm

COPY equivs-dummy.equivs /tmp/equivs-dummy.equivs

RUN dpkg --add-architecture arm64 && \
    apt-get update && \
    apt-get full-upgrade --no-install-recommends -y equivs && \
    equivs-build /tmp/equivs-dummy.equivs && \
    apt-get full-upgrade --no-install-recommends -y \
        build-essential crossbuild-essential-arm64 default-jdk-headless git \
        cmake debhelper devscripts lintian swig pkgconf:arm64 python-is-python3 \
        python3-dev:arm64 libjson-c-dev:arm64 libstdc++6:arm64 /equivs-dummy_1.0_all.deb && \
    adduser --gecos runner --disabled-password runner && \
    rm -rf /var/lib/apt/lists/*
