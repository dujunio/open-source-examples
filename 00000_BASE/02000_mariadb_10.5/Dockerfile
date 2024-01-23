#MariaDB 10.5

FROM dujunio/debian:12.4
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    apt-get install mariadb-server-10.5 -y &&\
    sed -i "s/# port = /port = /g" /etc/mysql/mariadb.cnf &&\
    sed -i "s/socket = /# socket = /g" /etc/mysql/mariadb.cnf &&\
    sed -i "s/bind-address /# bind-address /g" /etc/mysql/mariadb.conf.d/50-server.cnf &&\
    /etc/init.d/mariadb start &&\
    mysql -e "CREATE USER 'admin'@'%' IDENTIFIED BY 'Abcd1234$'; GRANT ALL PRIVILEGES ON *.* TO 'admin'@'%';"

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD netstat -atn | grep 3306

EXPOSE 3306
