#Redis 7.0

FROM dujunio/debian:12.4
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    apt-get install redis-server=5:7.0.11-1+deb12u1 -y &&\
    sed -i "s/bind 127.0.0.1 ::1/#bind 127.0.0.1 ::1/g" /etc/redis/redis.conf &&\
    sed -i "s/protected-mode yes/protected-mode no/g" /etc/redis/redis.conf

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD netstat -atn | grep 6379

EXPOSE 6379
