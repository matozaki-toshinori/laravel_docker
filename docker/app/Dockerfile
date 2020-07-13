FROM php:7.3.0-fpm
COPY app/php.ini /usr/local/etc/php/
# Pre-requisites installation
RUN apt-get update \
   && apt-get install -y libmcrypt-dev curl mcrypt git unzip zlib1g-dev libzip-dev zip \
   && pecl install mcrypt-1.0.2 \
   && docker-php-ext-install pdo_mysql bcmath zip \
   && docker-php-ext-enable mcrypt bcmath pdo_mysql sodium zip

# Composer installation
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

ENV COMPOSER_ALLOW_SUPERUSER 1
ENV COMPOSER_HOME /composer
ENV PATH $PATH:/composer/vendor/bin

RUN composer global require "laravel/installer"