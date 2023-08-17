#Tomcat 9.0.79 / JRE 8，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN /install/install

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=10s --retries=10 CMD curl -f http://localhost:8080
