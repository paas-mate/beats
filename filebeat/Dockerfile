FROM shoothzj/base:latest

ARG TARGETARCH

ENV FILEBEAT_HOME /opt/filebeat

ARG amd_download=7.17.9-linux-x86_64

ARG arm_download=7.17.9-linux-arm64

RUN if [ "$TARGETARCH" = "amd64" ]; \
    then download=$amd_download; \
    else download=$arm_download; \
    fi && \
    wget https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-$download.tar.gz && \
    mkdir /opt/filebeat && \
    tar -xf filebeat-$download.tar.gz -C /opt/filebeat --strip-components 1 && \
    rm -rf /opt/filebeat-$download.tar.gz;

WORKDIR /opt/filebeat
