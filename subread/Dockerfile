################## BASE IMAGE ######################
FROM biocontainers/biocontainers:v1.2.0_cv1

################## METADATA ######################
LABEL base_image="biocontainers:v1.2.0"
LABEL version="1"
LABEL software="subread"
LABEL software.version="2.0.1"

################## INSTALLATION ######################
USER root

ENV DEBIAN_FRONTEND noninteractive

RUN apt update && \
    apt upgrade -y

RUN conda install -c bioconda subread==2.0.1

# Change user
USER biodocker

WORKDIR /data/