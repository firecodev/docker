FROM docker.io/library/php:8-fpm-alpine

RUN apk add --update shadow tzdata

RUN userdel xfs && usermod -u 33 www-data && groupmod -g 33 www-data

ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

RUN chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions gd mysqli pdo_mysql
