FROM adminer:4.8.0
# WATCH OUT WHEN UPGRADING, THE SED BELOW MIGHT STOP WORKING

LABEL maitainer="jehan.labs@gmail.com"

USER root

RUN apk add autoconf gcc g++ make libffi-dev openssl-dev
RUN pecl install mongodb
RUN echo "extension=mongodb.so" > /usr/local/etc/php/conf.d/docker-php-ext-mongodb.ini

USER adminer
CMD	[ "php", "-S", "[::]:8080", "-t", "/var/www/html" ]

EXPOSE 8080