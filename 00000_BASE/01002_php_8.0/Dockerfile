#PHP 8.0，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    curl -sSL https://packages.sury.org/php/README.txt | bash -x &&\
    apt-get install php8.0 php8.0-fpm php8.0-curl php8.0-xml php8.0-gd php8.0-mbstring php8.0-mysql php8.0-redis php8.0-swoole php8.0-bcmath php8.0-gd php8.0-zip -y &&\
    sed -i "s/listen = \/run\/php\/php8.0-fpm.sock/listen = 0.0.0.0:9000/g" /etc/php/8.0/fpm/pool.d/www.conf &&\
    sed -i "s/memory_limit = 128M/memory_limit = 4096M/g" /etc/php/8.0/fpm/php.ini &&\
    sed -i "s/post_max_size = 8M/post_max_size = 1024M/g" /etc/php/8.0/fpm/php.ini &&\
    sed -i "s/post_max_size = 8M/post_max_size = 1024M/g" /etc/php/8.0/cli/php.ini &&\
    sed -i "s/upload_max_filesize = 2M/upload_max_filesize = 1024M/g" /etc/php/8.0/fpm/php.ini &&\
    sed -i "s/upload_max_filesize = 2M/upload_max_filesize = 1024M/g" /etc/php/8.0/cli/php.ini &&\
    echo "swoole.use_shortname = 'Off'" >> /etc/php/8.0/cli/conf.d/25-swoole.ini

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD netstat -atn | grep 9000

EXPOSE 9000
