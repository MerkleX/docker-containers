FROM ubuntu:18.04

RUN apt-get update && \
  apt-get install -y python python-pip curl && \
  pip install awscli --upgrade --user && \
  rm -rf /var/lib/apt/lists/*

ENV PATH /root/.local/bin:$PATH
