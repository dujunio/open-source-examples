#CoreBlog

FROM busybox
MAINTAINER dujun

ADD data.txz /

RUN chown -fR www-data:www-data /wwwroot/app &&\
    chmod -fR 755 /wwwroot/app/storage &&\
    chmod -fR 755 /wwwroot/app/bootstrap/cache
