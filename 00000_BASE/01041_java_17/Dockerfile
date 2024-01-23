#OpenJDK 17

FROM dujunio/debian:12.4
MAINTAINER dujun

ADD data1.txz /
ADD data2.txz /

ENV PATH=/opt/jdk-17.0.2/bin:/opt/apache-maven-3.9.2/bin:$PATH

ENTRYPOINT /entrypoint
