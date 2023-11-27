#JDK 20，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN bash /install/install

ENV PATH=/usr/lib/jvm/jdk-20/bin:/opt/apache-maven-3.9.2/bin:$PATH

ENTRYPOINT /entrypoint
