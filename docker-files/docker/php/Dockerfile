FROM php:7.2-fpm

LABEL maintainer="Chris Fidao"

RUN useradd -ms /bin/bash -u 1337 vessel
WORKDIR /var/www/html

RUN php -r "readfile('http://getcomposer.org/installer');" | php -- --install-dir=/usr/bin/ --filename=composer

COPY php-fpm.conf /etc/php/7.2/fpm/php-fpm.conf
COPY xdebug.ini /etc/php/7.2/mods-available/xdebug.ini

ENTRYPOINT ["php-fpm"]
