FROM ubuntu:20.04

RUN apt update && apt install gcc python3 pip -y 

RUN pip install scanpy==1.7.2
RUN pip install numpy==1.21
RUN ln -s /usr/bin/python3 /usr/bin/python

WORKDIR /data/