#PostgreSQL 13，基于 dujunio/debian

FROM dujunio/debian:11.7
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    apt-get install sudo postgresql-13 postgresql-client-13 -y &&\
    echo "listen_addresses = '*'" >> /etc/postgresql/13/main/postgresql.conf &&\
    sed -i "s/ssl = on/ssl = off/g" /etc/postgresql/13/main/postgresql.conf &&\
    echo "host    all         all         0.0.0.0/0      md5" >> /etc/postgresql/13/main/pg_hba.conf &&\
    /etc/init.d/postgresql start &&\
    sudo -u postgres createuser -s admin &&\
    sudo -u postgres createdb app &&\
    sudo -u postgres psql -c "alter user admin with password 'Abcd1234$'"

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD netstat -atn | grep 5432

EXPOSE 5432
