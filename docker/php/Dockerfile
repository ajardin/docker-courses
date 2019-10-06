FROM php:7.3-fpm-alpine

# Install Symfony requirements
RUN \
    apk add --no-cache \
        icu-libs \
        libzip-dev && \
    apk add --no-cache --virtual .build-deps \
        ${PHPIZE_DEPS} \
        icu-dev && \
    docker-php-ext-install -j "$(nproc)" \
        bcmath \
        intl \
        opcache \
        pdo_mysql \
        zip && \
    apk del .build-deps

## Install Composer globally
ENV COMPOSER_ALLOW_SUPERUSER 1
RUN \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    composer config --global repos.packagist composer https://repo.packagist.org
ENV PATH "${PATH}:/root/.composer/vendor/bin"
