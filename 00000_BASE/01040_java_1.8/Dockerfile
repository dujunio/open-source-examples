#JDK 1.8

FROM dujunio/debian:12.4
MAINTAINER dujun

ADD data.txz /

RUN bash /install/install

ENV PATH=/opt/jdk1.8.0_202/bin:/opt/apache-maven-3.9.2/bin:$PATH

ENTRYPOINT /entrypoint
