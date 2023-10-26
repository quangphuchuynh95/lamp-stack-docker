FROM php:5.5.33-apache

COPY php.ini "$PHP_INI_DIR/php.ini"

RUN apt-get update -y && apt-get install -y libpq-dev git

RUN docker-php-ext-install bcmath pdo pdo_mysql mysqli

RUN docker-php-ext-install MySQL

RUN a2enmod rewrite
