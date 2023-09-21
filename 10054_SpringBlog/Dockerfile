#SpringBlog

FROM busybox
MAINTAINER dujun

ADD data1.txz /
ADD data2.txz /

RUN cat /wwwroot/app.jar.part* > /wwwroot/app.jar &&\
    rm -f /wwwroot/app.jar.part*
