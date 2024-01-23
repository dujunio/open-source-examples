#Nginx 1.22

FROM dujunio/debian:12.4
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    apt-get install nginx=1.22* -y &&\
    sed -i "s/http {/http {\nclient_max_body_size 1024M;/g" /etc/nginx/nginx.conf

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=10s --retries=10 CMD curl -f http://localhost
