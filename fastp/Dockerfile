################## BASE IMAGE ######################
FROM biocontainers/biocontainers:v1.2.0_cv1

################## METADATA ######################
LABEL base_image="biocontainers:v1.2.0"
LABEL version="1"
LABEL software="fastp"
LABEL software.version="0.23.2"
LABEL about.summary="A tool designed to provide fast all-in-one preprocessing for FastQ files"
LABEL about.home="https://github.com/OpenGene/fastp/"
LABEL about.documentation="https://github.com/OpenGene/fastp/"
LABEL about.license_file="https://github.com/OpenGene/fastp/"
LABEL about.license="SPDX:GPL-3.0"
LABEL extra.identifiers.biotools="fastp"
LABEL about.tags="Genomics"
LABEL extra.binaries="fastp"

################## INSTALLATION ######################
USER root

ENV DEBIAN_FRONTEND noninteractive

RUN apt update && \
    apt upgrade -y && \
    apt install -y gcc libdeflate0 libisal2

RUN wget https://anaconda.org/bioconda/fastp/0.23.1/download/linux-64/fastp-0.23.1-h79da9fb_0.tar.bz2

RUN conda install ./fastp-0.23.1-h79da9fb_0.tar.bz2

# Change user
USER biodocker

WORKDIR /data/