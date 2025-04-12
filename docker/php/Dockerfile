FROM php:8.3-fpm

# Установка зависимостей
RUN apt-get update && apt-get install -y \
    git unzip curl libzip-dev libicu-dev libpq-dev libonig-dev libxml2-dev libssl-dev \
    libcurl4-openssl-dev libpng-dev libjpeg-dev libfreetype6-dev \
    && docker-php-ext-install intl pdo pdo_mysql zip opcache \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd

# Установка Composer
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/facet
