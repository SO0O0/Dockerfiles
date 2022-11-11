FROM php:8.0-apache

# Install system dependencies
RUN apt update \
    && apt install -y \
    g++ \
    libicu-dev \
    libpq-dev \
    libzip-dev \
    zip \
    zlib1g-dev \
    && docker-php-ext-install \
    intl \
    opcache \
    pdo \
    pdo_pgsql \
    pgsql
RUN apt-get update \
    && apt-get install -y git

# Set working directory
WORKDIR /var/www/designage

# Copy files
COPY . /var/www/designage/

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
