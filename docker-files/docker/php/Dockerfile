FROM php:7.2-fpm

LABEL maintainer="Chris Fidao"

WORKDIR /var/www/html

RUN useradd -ms /bin/bash -u 1337 vessel \
    && php -r "readfile('http://getcomposer.org/installer');" | php -- --install-dir=/usr/bin/ --filename=composer \
    && docker-php-ext-install pdo pdo_mysql mysqli \
    && pecl install xdebug-2.6.0 && docker-php-ext-enable mysqli xdebug \
    && apt-get update \
    && apt-get install -y curl zip unzip git \
    && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

COPY php-fpm.conf /etc/php/7.2/fpm/php-fpm.conf
COPY xdebug.ini /etc/php/7.2/mods-available/xdebug.ini

ENTRYPOINT ["php-fpm"]
