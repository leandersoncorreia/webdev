FROM php:5.6-fpm
COPY ./config/91-xdebug.ini /usr/local/etc/php/conf.d/91-xdebug.ini

RUN apt -qy install $PHPIZE_DEPS \
    && pecl install xdebug-2.5.5 \
    && docker-php-ext-install mysql pdo_mysql  \
    && docker-php-ext-enable mysql pdo_mysql xdebug

EXPOSE 9000
RUN usermod -u 1000 www-data
