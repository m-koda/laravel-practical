FROM php:7.3-fpm-alpine3.11

## https://github.com/docker-library/php/issues/344#issuecomment-364843883
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN set -eux \
  && docker-php-ext-install pdo_mysql \
  && rm -rf /tmp/*

RUN mkdir /var/www/src
WORKDIR /var/www/src
