#PHP 5.6，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    curl -sSL https://packages.sury.org/php/README.txt | bash -x &&\
    apt-get install php5.6 php5.6-fpm php5.6-mysql php5.6-mbstring php5.6-curl php5.6-xml php5.6-mcrypt php5.6-gd -y &&\
    sed -i "s/listen = \/run\/php\/php5.6-fpm.sock/listen = 0.0.0.0:9000/g" /etc/php/5.6/fpm/pool.d/www.conf

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD netstat -atn | grep 9000

EXPOSE 9000
