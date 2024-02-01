#PHP 7.4

FROM dujunio/debian:11.7
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    curl -sSL https://packages.sury.org/php/README.txt | bash -x &&\
    apt-get install php7.4 php7.4-fpm php7.4-mysql php7.4-mbstring php7.4-curl php7.4-xml php7.4-gd php7.4-sqlite3 php7.4-gmp php7.4-bcmath php7.4-zip php7.4-intl php7.4-enchant php7.4-redis php7.4-swoole imagemagick -y &&\
    sed -i "s/listen = \/run\/php\/php7.4-fpm.sock/listen = 0.0.0.0:9000/g" /etc/php/7.4/fpm/pool.d/www.conf &&\
    sed -i "s/memory_limit = 128M/memory_limit = 4096M/g" /etc/php/7.4/fpm/php.ini &&\
    sed -i "s/post_max_size = 8M/post_max_size = 1024M/g" /etc/php/7.4/fpm/php.ini &&\
    sed -i "s/post_max_size = 8M/post_max_size = 1024M/g" /etc/php/7.4/cli/php.ini &&\
    sed -i "s/upload_max_filesize = 2M/upload_max_filesize = 1024M/g" /etc/php/7.4/fpm/php.ini &&\
    sed -i "s/upload_max_filesize = 2M/upload_max_filesize = 1024M/g" /etc/php/7.4/cli/php.ini &&\
    sed -i "s/disable_functions =/;disable_functions =/g" /etc/php/7.4/fpm/php.ini &&\
    sed -i "s/disable_functions =/;disable_functions =/g" /etc/php/7.4/cli/php.ini &&\
    sed -i "s/;date.timezone =/date.timezone = Asia\/Shanghai/g" /etc/php/7.4/fpm/php.ini &&\
    sed -i "s/;date.timezone =/date.timezone = Asia\/Shanghai/g" /etc/php/7.4/cli/php.ini &&\
    curl -sS https://getcomposer.org/installer | php &&\
    mv composer.phar /usr/local/bin/composer &&\
    composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD netstat -atn | grep 9000

EXPOSE 9000
