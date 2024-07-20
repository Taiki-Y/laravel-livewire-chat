FROM php:8.3.9-fpm

ENV TZ Asia/Tokyo

RUN apt-get update && \
    apt-get -y install \
    git \
    zip \
    unzip \
    vim \
    && docker-php-ext-install pdo_mysql bcmath

COPY ./docker/app/php.ini /usr/local/etc/php/php.ini

COPY --from=composer:2.7.7 /usr/bin/composer /usr/bin/composer

WORKDIR /app