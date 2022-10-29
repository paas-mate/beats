FROM shoothzj/base:latest

ARG TARGETARCH

ENV HEARTBEAT_HOME /opt/heartbeat

ARG amd_download=8.4.3-linux-x86_64

ARG arm_download=8.4.3-linux-arm64

RUN if [ "$TARGETARCH" = "amd64" ]; \
    then download=$amd_download; \
    else download=$arm_download; \
    fi && \
    wget https://artifacts.elastic.co/downloads/beats/heartbeat/heartbeat-$download.tar.gz && \
    mkdir /opt/heartbeat && \
    tar -xf heartbeat-$download.tar.gz -C /opt/heartbeat --strip-components 1 && \
    rm -rf /opt/heartbeat-$download.tar.gz

WORKDIR /opt/heartbeat
