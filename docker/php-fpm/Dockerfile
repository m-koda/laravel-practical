FROM php:7.3.17-fpm-alpine3.11

## https://github.com/docker-library/php/issues/344#issuecomment-364843883
## composerは別コンテナにしてもいいかも
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

## apline3.3以降であればapk addに--no-cacheを使うことでrm -rf /var/cache/apk/*は不要
RUN set -eux \
  && docker-php-ext-install -j$(nproc) pdo_mysql \
  && rm -rf /var/cache/apk/*

RUN mkdir /var/www/src
WORKDIR /var/www/src
