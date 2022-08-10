FROM ttbb/base

ENV HEARTBEAT_HOME /opt/sh/heartbeat

ARG amd_download=7.17.5-linux-x86_64

ARG arm_download=7.17.5-linux-arm64

RUN if [[ "$TARGETARCH" = "amd64" ]]; \
    then download=$amd_download; \
    else download=$arm_download; \
    fi && \
    wget https://artifacts.elastic.co/downloads/beats/heartbeat/heartbeat-$download.tar.gz && \
    mkdir /opt/sh/heartbeat && \
    tar -xf heartbeat-$download.tar.gz -C /opt/sh/heartbeat --strip-components 1 && \
    rm -rf /opt/sh/heartbeat-$download.tar.gz

WORKDIR /opt/sh/heartbeat