#PHP 5.6

FROM dujunio/debian:12.4
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    curl -sSL https://packages.sury.org/php/README.txt | bash -x &&\
    apt-get install php5.6 php5.6-fpm php5.6-mysql php5.6-mbstring php5.6-curl php5.6-xml php5.6-mcrypt php5.6-gd php5.6-sqlite3 php5.6-imagick php5.6-bcmath -y &&\
    sed -i "s/listen = \/run\/php\/php5.6-fpm.sock/listen = 0.0.0.0:9000/g" /etc/php/5.6/fpm/pool.d/www.conf &&\
    sed -i "s/memory_limit = 128M/memory_limit = 4096M/g" /etc/php/5.6/fpm/php.ini &&\
    sed -i "s/post_max_size = 8M/post_max_size = 1024M/g" /etc/php/5.6/fpm/php.ini &&\
    sed -i "s/post_max_size = 8M/post_max_size = 1024M/g" /etc/php/5.6/cli/php.ini &&\
    sed -i "s/upload_max_filesize = 2M/upload_max_filesize = 1024M/g" /etc/php/5.6/fpm/php.ini &&\
    sed -i "s/upload_max_filesize = 2M/upload_max_filesize = 1024M/g" /etc/php/5.6/cli/php.ini

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD netstat -atn | grep 9000

EXPOSE 9000
