FROM php:8.0-rc-fpm-alpine3.15

COPY ./config/opcache.ini /usr/local/etc/php/conf.d/docker-php-ext-opcache.ini

RUN apk update && apk upgrade \
    #   Включаем необходимые расширения
    && docker-php-ext-install pdo pdo_mysql opcache

COPY ./config/opcache.ini /usr/local/etc/php/conf.d/docker-php-ext-opcache.ini

RUN curl -sS https://getcomposer.org/installer | php -- \
    --install-dir=/usr/bin --filename=composer && chmod +x /usr/bin/composer

WORKDIR /var/www/laravel