FROM php:7.3.2-fpm

RUN apt-get update && apt-get install -y \
        libzip-dev \
        zip \
	&& docker-php-ext-configure zip --with-libzip \
	&& docker-php-ext-install zip \
	&& docker-php-ext-install mysqli \
	&& docker-php-ext-install bcmath \
	&& docker-php-ext-install pdo_mysql

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/html
