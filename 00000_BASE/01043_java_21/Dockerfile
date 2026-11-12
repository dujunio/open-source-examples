#JDK 21

FROM dujunio/debian:12.4
MAINTAINER dujun

ADD data.txz /

RUN bash /install/install

ENV PATH=/usr/lib/jvm/jdk-21-oracle-x64/bin:/opt/apache-maven-3.9.9/bin:$PATH

ENTRYPOINT /entrypoint
