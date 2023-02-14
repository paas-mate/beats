FROM shoothzj/base:latest

ARG TARGETARCH

ENV METRICBEAT_HOME /opt/metricbeat

ARG amd_download=7.17.9-linux-x86_64

ARG arm_download=7.17.9-linux-arm64

RUN if [ "$TARGETARCH" = "amd64" ]; \
    then download=$amd_download; \
    else download=$arm_download; \
    fi && \
    wget https://artifacts.elastic.co/downloads/beats/metricbeat/metricbeat-$download.tar.gz && \
    mkdir /opt/metricbeat && \
    tar -xf metricbeat-$download.tar.gz -C /opt/metricbeat --strip-components 1 && \
    rm -rf /opt/metricbeat-$download.tar.gz

WORKDIR /opt/metricbeat
