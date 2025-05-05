#Turso 1.0，基于 dujunio/debian

FROM dujunio/debian:12.4
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    apt-get install xz-utils -y &&\
    curl -sSfL https://get.tur.so/install.sh | bash

ENTRYPOINT /entrypoint

EXPOSE 8080
