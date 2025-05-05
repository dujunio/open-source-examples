#Turso 1.0，基于 dujunio/debian

FROM dujunio/debian:12.4
MAINTAINER dujun

ADD data.txz /

RUN bash /install

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD netstat -atn | grep 8080

EXPOSE 8080
