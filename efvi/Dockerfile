FROM ubuntu:18.04

USER root
RUN apt-get update
RUN apt-get install -y wget build-essential cmake autoconf automake
RUN wget https://www.openonload.org/download/openonload-201805.tgz
RUN mkdir /build && mv openonload-201805.tgz /build
WORKDIR /build
RUN tar -xvf openonload-201805.tgz
WORKDIR /build/openonload-201805/scripts
RUN ./onload_build --user
WORKDIR /build/openonload-201805/build/gnu_x86_64
RUN cp lib/ciul/libciul1.a /usr/local/lib/
RUN cp lib/citools/libcitools1.a /usr/local/lib
WORKDIR /build/openonload-201805/src/include
RUN cp -r ci /usr/local/include/
RUN cp -r etherfabric /usr/local/include/
WORKDIR /
RUN rm -rf /build
RUN apt-get remove -y wget build-essential cmake autoconf automake
RUN apt-get autoremove -y
