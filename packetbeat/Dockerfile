FROM ttbb/base

ENV PACKETBEAT_HOME /opt/sh/packetbeat

ARG amd_download=7.17.5-linux-x86_64

ARG arm_download=7.17.5-linux-arm64

RUN if [[ "$TARGETARCH" = "amd64" ]]; \
    then download=$amd_download; \
    else download=$arm_download; \
    fi && \
    wget https://artifacts.elastic.co/downloads/beats/packetbeat/packetbeat-$download.tar.gz && \
    mkdir /opt/sh/packetbeat && \
    tar -xf packetbeat-$download.tar.gz -C /opt/sh/packetbeat --strip-components 1 && \
    rm -rf /opt/sh/packetbeat-$download.tar.gz

ENV HEARTBEAT_HOME /opt/sh/packetbeat

WORKDIR /opt/sh/packetbeat