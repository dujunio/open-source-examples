#PHP 7.2，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    curl -sSL https://packages.sury.org/php/README.txt | bash -x &&\
    apt-get install php7.2 php7.2-fpm php7.2-mysql php7.2-mbstring php7.2-curl php7.2-xml php7.2-gd php7.2-sqlite3 php7.2-gmp php7.2-bcmath php7.2-zip php7.2-intl php7.2-enchant php7.2-redis imagemagick -y &&\
    sed -i "s/listen = \/run\/php\/php7.2-fpm.sock/listen = 0.0.0.0:9000/g" /etc/php/7.2/fpm/pool.d/www.conf &&\
    sed -i "s/memory_limit = 128M/memory_limit = 4096M/g" /etc/php/7.2/fpm/php.ini &&\
    sed -i "s/post_max_size = 8M/post_max_size = 1024M/g" /etc/php/7.2/fpm/php.ini &&\
    sed -i "s/post_max_size = 8M/post_max_size = 1024M/g" /etc/php/7.2/cli/php.ini &&\
    sed -i "s/upload_max_filesize = 2M/upload_max_filesize = 1024M/g" /etc/php/7.2/fpm/php.ini &&\
    sed -i "s/upload_max_filesize = 2M/upload_max_filesize = 1024M/g" /etc/php/7.2/cli/php.ini &&\
    curl -sS https://getcomposer.org/installer | php &&\
    mv composer.phar /usr/local/bin/composer &&\
    composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD netstat -atn | grep 9000

EXPOSE 9000
