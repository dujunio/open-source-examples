#MongoDB 4.4

FROM dujunio/debian:11.7
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    apt-get install gnupg2 -y &&\
    curl -sL https://www.mongodb.org/static/pgp/server-4.4.asc | apt-key add - &&\
    echo "deb http://repo.mongodb.org/apt/debian buster/mongodb-org/4.4 main" | tee /etc/apt/sources.list.d/mongodb-org.list &&\
    apt-get update -y &&\
    apt-get install -y mongodb-org mongosh systemctl &&\
    sed -i "s/127.0.0.1/0.0.0.0/g" /etc/mongod.conf

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD netstat -atn | grep 27017

EXPOSE 27017
