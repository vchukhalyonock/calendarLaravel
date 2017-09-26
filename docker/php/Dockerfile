FROM php:7.0.23-fpm

RUN apt-get update && \
    apt-get install -yqq libmcrypt-dev libpng-dev && \
    docker-php-ext-install mysqli && \
    docker-php-ext-install mcrypt && \
    docker-php-ext-install -j5 gd mbstring pdo pdo_mysql shmop

RUN pecl install xdebug
RUN docker-php-ext-enable xdebug


RUN sed -ri 's/^www-data:x:33:33:/www-data:x:1000:50:/' /etc/passwd
RUN chown -R 1000:1000 /tmp