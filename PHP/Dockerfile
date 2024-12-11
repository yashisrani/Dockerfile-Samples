# Use a PHP base image
FROM php:8.2-apache

# Enable Apache mod_rewrite for Laravel or similar frameworks
RUN a2enmod rewrite

# Set working directory
WORKDIR /var/www/html

# Copy application code
COPY . .

# Install dependencies if using Composer
COPY composer.json composer.lock ./
RUN apt-get update && \
    apt-get install -y unzip && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    composer install --no-dev --optimize-autoloader

# Set permissions for web server
RUN chown -R www-data:www-data /var/www/html

# Expose the port
EXPOSE 80

# Start Apache
CMD ["apache2-foreground"]
