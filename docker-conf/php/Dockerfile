FROM php:7.2-fpm
MAINTAINER Riccardo Tartaglia <tartaglia.riccardo@gmail.com>

######
# install php extensions using docker-php-ext-install
######
RUN apt-get update && apt-get install -y \
        zlib1g-dev \
        libpq-dev \
        git \
        libicu-dev \
        libxml2-dev \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
    && docker-php-ext-install iconv zip xml intl pdo mysqli pdo_mysql \
    && docker-php-ext-enable mysqli pdo_mysql \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd

# composer
RUN curl --insecure https://getcomposer.org/composer.phar -o /usr/bin/composer && chmod +x /usr/bin/composer

# Set timezone
RUN rm /etc/localtime
RUN ln -s /usr/share/zoneinfo/Europe/Berlin /etc/localtime
RUN "date"