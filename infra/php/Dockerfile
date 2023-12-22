FROM php:8.2-fpm

WORKDIR /var/www/html

ENV COMPOSER_ALLOW_SUPERUSER=1
ENV DB_USERNAME=root
ENV DB_PASSWORD=root
ENV DB_HOST=database

RUN apt-get update && apt-get install -y \
    libzip-dev \
    unzip \
    && docker-php-ext-install zip pdo_mysql

COPY --from=composer /usr/bin/composer /usr/bin/composer

COPY ./ /var/www/html

COPY ./infra/php/php.ini /usr/local/etc/php/conf.d/

RUN composer install --no-interaction --optimize-autoloader

RUN php artisan key:generate

RUN chown -R www-data:www-data /var/www/html/storage /var/www/html/bootstrap/cache

EXPOSE 9000

CMD ["php-fpm"]

