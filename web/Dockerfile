FROM php:5.5.38-apache

ENV APACHE_DOCUMENT_ROOT /var/www/html

RUN mv "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini"

RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf

RUN apt-get update -y && apt-get install -y libpq-dev git

RUN docker-php-ext-install bcmath pdo pdo_mysql mysqli

RUN a2enmod rewrite
