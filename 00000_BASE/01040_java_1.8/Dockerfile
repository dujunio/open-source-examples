#JDK 1.8，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN bash /install/install

ENV PATH=/opt/jdk1.8.0_202/bin:/opt/apache-maven-3.9.2/bin:$PATH

ENTRYPOINT /entrypoint
