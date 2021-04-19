FROM php:8.0-fpm-alpine

RUN apk add bash
RUN apk add icu-dev

# extensions
RUN set -xe \
    && apk add --no-cache --update --virtual .phpize-deps $PHPIZE_DEPS \
    && apk add git \
    && docker-php-ext-install pdo_mysql intl \
    && rm -rf /usr/share/php \
    && rm -rf /tmp/* \
    && apk del  .phpize-deps
