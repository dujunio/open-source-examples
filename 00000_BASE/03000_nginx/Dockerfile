#Nginx，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    apt-get install nginx -y

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=10s --retries=10 CMD curl -f http://localhost
