FROM php:8.1-cli-alpine

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
        npm \
        openssh-client \
        zlib \
        zlib-dev && \
    docker-php-ext-configure gd --with-freetype=/usr/include/ --with-jpeg=/usr/include/ && \
    docker-php-ext-install zip intl gd opcache && \
    pecl install apcu-5.1.19 && \
    docker-php-ext-enable apcu && \
    composer self-update

COPY php.ini /usr/local/etc/php/
