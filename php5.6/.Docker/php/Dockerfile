FROM php:5.6-fpm-alpine

# Installing PHP Dependencies
RUN apk add --no-cache --virtual .build-deps \
        $PHPIZE_DEPS \
        curl-dev \
        imagemagick-dev \
        libtool \
        freetype-dev \
        libxml2-dev \
        libpng-dev \
        libjpeg-turbo-dev \
        sqlite-dev \
        libmcrypt-dev \
    && apk add --no-cache \
        curl \
        git \
        imagemagick \
        mysql-client \
        libintl \
        icu \
        icu-dev \
        libzip-dev \
    && pecl install imagick \
    && docker-php-ext-enable imagick \
    && docker-php-ext-install \
        bcmath \
        curl \
        iconv \
        mbstring \
        pdo \
        pdo_mysql \
        pdo_sqlite \
        pcntl \
        tokenizer \
        xml \
        zip \
        intl \
        mcrypt

# Install the PHP gd library
RUN docker-php-ext-install gd && \
    docker-php-ext-configure gd \
        --enable-gd-native-ttf \
        --with-jpeg-dir=/usr/lib \
        --with-freetype-dir=/usr/include/freetype2 && \
    docker-php-ext-install gd \
    && curl -s https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer

RUN pecl install mongo && docker-php-ext-enable mongo

RUN docker-php-ext-install calendar

RUN pecl install mongodb-1.7.4 \
    && docker-php-ext-enable mongodb

RUN mkdir -p /var/data/session


WORKDIR /var/www
