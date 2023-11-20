# Use the official PHP image with Apache
FROM php:apache

# Install required extensions and tools
RUN apt-get update \
    && apt-get install -y \
        libzip-dev \
        zip \
        unzip \
    && docker-php-ext-install zip pdo_mysql \
    && a2enmod rewrite

# Install Composer globally
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Set working directory
WORKDIR /workspace

# Expose port 80 for Apache
EXPOSE 80
