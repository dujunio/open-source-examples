#ELADMIN 2.6

FROM busybox
MAINTAINER dujun

ADD data1.txz /
ADD data2.txz /

RUN cat /wwwroot/server/jar.part* > /wwwroot/server/eladmin-system-2.6.jar &&\
    rm -f /wwwroot/server/jar.part* &&\
    chown -fR www-data:www-data /wwwroot/web
