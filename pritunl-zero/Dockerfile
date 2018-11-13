FROM ubuntu:18.04

RUN apt-get update && apt-get install -y gnupg

ADD install.sh ./
RUN bash install.sh
RUN mkdir -p /data/db
CMD mongod --fork --logpath /var/log/mongod.log && pritunl-zero start
