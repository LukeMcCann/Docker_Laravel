FROM php:7.2.2-fpm 

RUN apt-get update -y && apt-get install -y libcrypt-dev openssl
RUN docker-php-ext-install pdo mcrypt mbstring

RUN apt-get -y curl
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /app
COPY . /app

RUN composer install

CMD artisan serve --host=0.0.0.0 --port=8000 

EXPOSE 8000

