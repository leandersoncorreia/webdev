FROM php:7.4-fpm
COPY ./config/91-xdebug.ini /usr/local/etc/php/conf.d/91-xdebug.ini

RUN apt-get -y update \
    && apt-get install -y $PHPIZE_DEPS  \
      libicu-dev  \
      libpng-dev  \
      libzip-dev  \
      libxml2-dev\
    && pecl install xdebug  \
      redis \
    && docker-php-ext-configure intl \
    && docker-php-ext-install intl  \
      mysqli  \
      pdo_mysql  \
      opcache  \
      zip  \
      bcmath  \
      soap  \
      gd \
    && docker-php-ext-enable mysqli  \
      pdo_mysql  \
      xdebug  \
      redis


EXPOSE 9000 9003
RUN usermod -u 1000 www-data
