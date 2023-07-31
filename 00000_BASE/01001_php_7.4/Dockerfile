#PHP 7.4，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    curl -sSL https://packages.sury.org/php/README.txt | bash -x &&\
    apt-get install php7.4 php7.4-fpm php7.4-mysql php7.4-mbstring php7.4-curl php7.4-xml php7.4-gd php7.4-sqlite3 php7.4-gmp php7.4-bcmath php7.4-zip php7.4-intl php7.4-enchant imagemagick -y &&\
    sed -i "s/listen = \/run\/php\/php7.4-fpm.sock/listen = 0.0.0.0:9000/g" /etc/php/7.4/fpm/pool.d/www.conf

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD netstat -atn | grep 9000

EXPOSE 9000
