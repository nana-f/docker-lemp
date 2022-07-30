FROM php:8.1-fpm
 
COPY ./docker/php/php.ini /usr/local/etc/app/php.ini
 
COPY --from=composer:2.2.9 /usr/bin/composer /usr/bin/composer
 
RUN apt-get update && apt-get install -y \
    zip \
    unzip
 
RUN docker-php-ext-install bcmath \
    pdo_mysql

RUN curl https://deb.nodesource.com/setup_17.x | bash -
RUN apt-get install -y nodejs
RUN npm install npm@latest -g
 
WORKDIR /var/www/html