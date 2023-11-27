#OpenJDK 17，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data1.txz /
ADD data2.txz /

ENV PATH=/opt/jdk-17.0.2/bin:/opt/apache-maven-3.9.2/bin:$PATH

ENTRYPOINT /entrypoint
