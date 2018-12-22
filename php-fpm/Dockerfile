######
# See: https://hub.docker.com/_/php/
######

FROM php:7.3.0-fpm
MAINTAINER rere <748691045@qq.com>

######
# You can install php extensions using docker-php-ext-install
######

RUN curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
        git \
    	nodejs \
    	zip \
#    && docker-php-ext-install -j$(nproc) iconv mcrypt \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd 

#composer
RUN curl -sL https://getcomposer.org/installer | php -- --install-dir /usr/bin --filename composer