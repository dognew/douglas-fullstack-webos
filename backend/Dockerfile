# Usamos a mesma versão 8.3 do seu LiteSpeed
FROM php:8.3-fpm

# Instalando extensões essenciais
RUN apt-get update && apt-get install -y \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \
    zip \
    unzip \
    git \
    curl

# Extensões para o Laravel e MySQL
RUN docker-php-ext-install pdo_mysql gd bcmath

WORKDIR /var/www

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

EXPOSE 8000
CMD php artisan serve --host=0.0.0.0 --port=8000