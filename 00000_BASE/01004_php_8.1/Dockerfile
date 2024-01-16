#PHP 8.1，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    curl -sSL https://packages.sury.org/php/README.txt | bash -x &&\
    apt-get install php8.1 php8.1-fpm php8.1-mysql php8.1-redis php8.1-mbstring php8.1-curl php8.1-xml php8.1-gd php8.1-zip php8.1-bcmath imagemagick php8.1-sqlite3 php8.1-yaml php8.1-imagick -y &&\
    sed -i "s/listen = \/run\/php\/php8.1-fpm.sock/listen = 0.0.0.0:9000/g" /etc/php/8.1/fpm/pool.d/www.conf &&\
    sed -i "s/memory_limit = 128M/memory_limit = 4096M/g" /etc/php/8.1/fpm/php.ini &&\
    sed -i "s/post_max_size = 8M/post_max_size = 1024M/g" /etc/php/8.1/fpm/php.ini &&\
    sed -i "s/post_max_size = 8M/post_max_size = 1024M/g" /etc/php/8.1/cli/php.ini &&\
    sed -i "s/upload_max_filesize = 2M/upload_max_filesize = 1024M/g" /etc/php/8.1/fpm/php.ini &&\
    sed -i "s/upload_max_filesize = 2M/upload_max_filesize = 1024M/g" /etc/php/8.1/cli/php.ini

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD netstat -atn | grep 9000

EXPOSE 9000
