FROM php:7.3-cli-alpine

RUN echo "http://dl-4.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories && \
    apk add --no-cache \
        autoconf \
        automake \
        build-base \
        composer \
        file \
        freetype-dev \
        gcc \
        git \
        gnupg \
        g++ \
        icu-dev \
        libjpeg-turbo \
        libjpeg-turbo-dev \
        libpng \
        libpng-dev \
        libtool \
        libwebp \
        libwebp-dev \
        libzip-dev \
        make \
        nasm \
        nodejs \
        nodejs-npm \
        openssh-client \
        zlib \
        zlib-dev && \
    docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ && \
    docker-php-ext-install zip intl gd opcache && \
    pecl install apcu-5.1.11 && \
    docker-php-ext-enable apcu && \
    composer self-update --1

COPY php.ini /usr/local/etc/php/
