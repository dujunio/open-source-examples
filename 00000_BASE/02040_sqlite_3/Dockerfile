#SQLite 3，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    apt-get install sqlite3 -y

ENTRYPOINT /entrypoint
