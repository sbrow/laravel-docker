FROM php:8.0
COPY --from=composer /usr/bin/composer /usr/bin/composer
RUN export DEBIAN_FRONTEND=noninteractive

# Install relevant packages
RUN apt-get update && apt-get install git libzip-dev zip -yq

# Install redis extension
RUN pecl install redis -y
RUN docker-php-ext-enable redis

# Install PHP extensions
RUN docker-php-ext-install bcmath pcntl pdo_mysql zip

# Install Node
RUN curl -fsSL https://deb.nodesource.com/setup_14.x | bash -
RUN apt-get install -y nodejs
