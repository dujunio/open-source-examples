#Turso 1.0，基于 dujunio/debian

FROM dujunio/debian:12.4
MAINTAINER dujun

ADD data.txz /

RUN bash /install

ENTRYPOINT /entrypoint

EXPOSE 8080
