FROM php:8.0
COPY --from=composer /usr/bin/composer /usr/bin/composer
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install git libzip-dev zip
RUN pecl install redis -y
RUN docker-php-ext-enable redis
RUN docker-php-ext-install bcmath pcntl pdo_mysql zip
