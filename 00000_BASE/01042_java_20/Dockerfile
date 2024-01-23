#JDK 20

FROM dujunio/debian:12.4
MAINTAINER dujun

ADD data.txz /

RUN bash /install/install

ENV PATH=/usr/lib/jvm/jdk-20/bin:/opt/apache-maven-3.9.2/bin:$PATH

ENTRYPOINT /entrypoint
