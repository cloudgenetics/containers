################## BASE IMAGE ######################
FROM biocontainers/biocontainers:v1.2.0_cv1

################## METADATA ######################
LABEL base_image="biocontainers:v1.2.0"
LABEL version="1"
LABEL software="samtools"
LABEL software.version="1.14"

################## INSTALLATION ######################
USER root

ENV DEBIAN_FRONTEND noninteractive

RUN apt update && \
    apt upgrade -y && \
    apt install -y libhts3 libncurses5-dev autoconf zlib1g-dev libbz2-dev liblzma-dev 

RUN ln -s /lib/x86_64-linux-gnu/libtic.so.6.2 /lib/x86_64-linux-gnu/libtinfow.so.6

RUN cd && wget https://github.com/samtools/samtools/releases/download/1.14/samtools-1.14.tar.bz2 && tar -xf samtools-1.14.tar.bz2 && \
    cd samtools-1.14 && autoheader && autoconf -Wno-syntax && ./configure && make -j8 && make install

# Change user
USER biodocker

WORKDIR /data/