#Docker，基于官方 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    apt-get install docker.io docker-compose -y

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=5s --timeout=3s --retries=5 CMD ps axu | grep [d]ocker
