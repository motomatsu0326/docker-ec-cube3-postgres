FROM php:7.1-apache

ENV DEBCONF_NOWARNINGS yes

RUN set -ex apk --no-cache add postgresql-dev libpq-dev
RUN apt-get update \
    && apt-get install -y zlib1g-dev libpq-dev git \
    && docker-php-ext-install pdo_mysql pdo_pgsql mysqli \
    && a2enmod rewrite

COPY --from=composer /usr/bin/composer /usr/bin/composer
