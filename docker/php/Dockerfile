FROM php:8.2-fpm

# APT UPDATE START #
RUN apt update \
    && apt install -y zlib1g-dev g++ git libicu-dev zip libzip-dev zip libxml2-dev curl \
    && docker-php-ext-install intl opcache pdo pdo_mysql \
    && pecl install apcu \
    && docker-php-ext-enable apcu \
    && docker-php-ext-configure zip \
    && docker-php-ext-install zip \
    && docker-php-ext-install soap
# APT UPDATE END #

# XDEBUG START #
COPY /conf.d/xdebug.ini /usr/local/etc/php/conf.d

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug
# XDEBUG END #

WORKDIR /var/www/html

# COMPOSER START #
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
# COMPOSER START #

# SYMFONY START #
RUN curl -sS https://get.symfony.com/cli/installer | bash
RUN mv /root/.symfony5/bin/symfony /usr/local/bin/symfony
# SYMFONY END #

# GIT CONFIG START #
RUN git config --global user.email "example@youremail.com"
RUN git config --global user.name "Your Name"
# GIT CONFIG END #