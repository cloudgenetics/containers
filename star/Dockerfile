################## BASE IMAGE ######################
FROM biocontainers/biocontainers:v1.2.0_cv1

################## METADATA ######################
LABEL base_image="biocontainers:v1.2.0"
LABEL version="1"
LABEL software="star"
LABEL software.version="2.7.9a"

################## INSTALLATION ######################
USER root

ENV DEBIAN_FRONTEND noninteractive

RUN apt update && \
    apt upgrade -y

RUN wget https://anaconda.org/bioconda/star/2.7.9a/download/linux-64/star-2.7.9a-h9ee0642_0.tar.bz2

RUN conda install ./star-2.7.9a-h9ee0642_0.tar.bz2

# Change user
USER biodocker

WORKDIR /data/