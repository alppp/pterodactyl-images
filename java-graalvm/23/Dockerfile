FROM        container-registry.oracle.com/graalvm/jdk:23

LABEL       org.opencontainers.image.source="https://github.com/alppp/pterodactyl-images"
LABEL       org.opencontainers.image.licenses="MIT"

RUN         microdnf update -y && \
            microdnf install -y lsof curl ca-certificates openssl git tar sqlite fontconfig freetype tzdata iproute libstdc++ glibc-langpack-en && \
            microdnf clean all && \
            useradd -d /home/container -m container

ENV         LANG=en_US.UTF-8
ENV         LC_ALL=en_US.UTF-8
ENV         LANGUAGE=en_US:en

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
