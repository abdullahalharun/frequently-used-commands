FROM php:8.2-fpm

# Install dependencies
RUN apt-get update && apt-get install -y \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip \
    git \
    && docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd

# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Set working directory
WORKDIR /var/www

# Copy application
COPY ../../lms-api-laravel /var/www

# Ensure the storage/logs directory exists and set permissions
RUN mkdir -p /var/www/storage/logs \
    && chown -R www-data:www-data /var/www \
    && chmod -R 775 /var/www/storage /var/www/bootstrap/cache

# Install PHP dependencies
RUN composer install --no-autoloader
RUN composer dump-autoload

COPY ../../lms-api-laravel/.env /var/www/.env
RUN php artisan key:generate

# php artisan config:cache
RUN php artisan optimize:clear

EXPOSE 9000

# Start PHP-FPM
CMD ["php-fpm"]