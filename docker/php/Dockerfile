FROM php:7.3-apache

RUN mv "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini" && \
    echo 'date.timezone = Europe/Berlin' >> "$PHP_INI_DIR/php.ini"

RUN apt-get update && apt-get install -my \
    git \
    zip \
    && rm -rf /var/lib/apt/lists/*

COPY ./docker/php/composer-installer.sh /tmp/
RUN /tmp/composer-installer.sh && rm /tmp/composer-installer.sh

WORKDIR /var/www

EXPOSE 80