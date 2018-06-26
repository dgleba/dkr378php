FROM php:7.2.2-apache

RUN apt-get update -y && apt-get install -y libpng-dev curl libcurl4-openssl-dev

RUN docker-php-ext-install pdo pdo_mysql gd curl

RUN a2enmod rewrite
RUN a2enmod autoindex
RUN service apache2 restart
