FROM php:5.6-fpm

COPY ./sources.list.jessie /etc/apt/sources.list

RUN apt-get update && apt-get install -y \
    && apt-get install -y zlib1g=1:1.2.8.dfsg-2+b1 --allow-downgrades \
    && apt-get install -y zlib1g-dev \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
    && docker-php-ext-install -j$(nproc) iconv mcrypt \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install pdo \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install mysqli
