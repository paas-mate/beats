FROM ttbb/base

ENV METRICBEAT_HOME /opt/sh/metricbeat

ARG amd_download=7.17.5-linux-x86_64

ARG arm_download=7.17.5-linux-arm64

RUN if [[ "$TARGETARCH" = "amd64" ]]; \
    then download=$amd_download; \
    else download=$arm_download; \
    fi && \
    wget https://artifacts.elastic.co/downloads/beats/metricbeat/metricbeat-$download.tar.gz && \
    mkdir /opt/sh/metricbeat && \
    tar -xf metricbeat-$download.tar.gz -C /opt/sh/metricbeat --strip-components 1 && \
    rm -rf /opt/sh/metricbeat-$download.tar.gz

WORKDIR /opt/sh/metricbeat