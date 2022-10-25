FROM shoothzj/base:latest

ENV PACKETBEAT_HOME /opt/packetbeat

ARG amd_download=8.4.3-linux-x86_64

ARG arm_download=8.4.3-linux-arm64

RUN if [ "$TARGETARCH" = "amd64" ]; \
    then download=$amd_download; \
    else download=$arm_download; \
    fi && \
    wget https://artifacts.elastic.co/downloads/beats/packetbeat/packetbeat-$download.tar.gz && \
    mkdir /opt/packetbeat && \
    tar -xf packetbeat-$download.tar.gz -C /opt/packetbeat --strip-components 1 && \
    rm -rf /opt/packetbeat-$download.tar.gz

ENV HEARTBEAT_HOME /opt/packetbeat

WORKDIR /opt/packetbeat
