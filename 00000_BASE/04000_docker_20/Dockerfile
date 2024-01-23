#Docker 20

FROM dujunio/debian:12.4
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    apt-get install docker.io=20.* docker-compose -y

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=5s --timeout=3s --retries=5 CMD ps axu | grep [d]ocker
