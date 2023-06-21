#Redis，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    apt-get install redis-server -y &&\
    sed -i "s/bind 127.0.0.1 ::1/#bind 127.0.0.1 ::1/g" /etc/redis/redis.conf &&\
    sed -i "s/protected-mode yes/protected-mode no/g" /etc/redis/redis.conf

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD netstat -atn | grep 6379

EXPOSE 6379
