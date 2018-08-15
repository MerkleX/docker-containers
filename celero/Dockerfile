FROM ubuntu:18.04

RUN apt-get update && \
  apt-get install -y build-essential cmake git wget unzip libncurses5-dev

RUN wget https://github.com/DigitalInBlue/Celero/archive/v2.3.0.zip
RUN unzip v2.3.0.zip && \
  cd Celero-2.3.0 && \
  mkdir -p build && \
  cd build && \
  cmake .. && \
  make install && \
  cd / && \
  rm -rf Celero-2.3.0

RUN apt-get remove -y build-essential cmake git wget unzip libncurses5-dev && \
  apt-get autoremove -y && \
  rm -rf /var/lib/apt/lists/*
