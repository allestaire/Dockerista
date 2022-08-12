FROM php:5.6-fpm-alpine

# COPY mongo-1.5.8.tgz /tmp/mongo.tgz

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

# Install MongoDB Driver
# RUN curl https://pecl.php.net/get/mongo-1.5.8.tgz > /tmp/mongo.tgz
# RUN tar -xpzf /tmp/mongo.tgz -C /tmp
# RUN mv /tmp/mongo-1.5.8 /usr/src/php/ext
# RUN docker-php-ext-install mongo-1.5.8

RUN pecl install mongo && docker-php-ext-enable mongo

RUN docker-php-ext-install calendar

RUN pecl install mongodb-1.7.4 \
    && docker-php-ext-enable mongodb

RUN mkdir -p /var/data/session

# COPY local.ini /usr/local/etc/php/conf.d/local.ini


WORKDIR /var/www
