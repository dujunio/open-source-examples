#PHP 8.2，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    curl -sSL https://packages.sury.org/php/README.txt | bash -x &&\
    apt-get install php8.2 php8.2-fpm php8.2-mysql php8.2-redis php8.2-mbstring php8.2-curl php8.2-xml php8.2-gd php8.2-zip php8.2-sqlite3 -y &&\
    sed -i "s/listen = \/run\/php\/php8.2-fpm.sock/listen = 0.0.0.0:9000/g" /etc/php/8.2/fpm/pool.d/www.conf

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD netstat -atn | grep 9000

EXPOSE 9000
