FROM php:7.3-fpm

LABEL maintainer="Volodymyr Kupriienko vldmr.kuprienko@gmail.com"

ARG COMPOSER_VERSION=2.0.11

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
	# Install libraries
    zlib1g-dev \
    libicu-dev \
    libzip-dev \

    # Install Git for installation private packages via Composer
    git \
    # Install text editor for work with composer.json
    nano && \

    # Install PHP extensions
    docker-php-ext-install zip intl && \

    # Install Composer
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION} && \

    # Install plugin for installation of composer packages parallel
    if echo ${COMPOSER_VERSION} | grep -Eq '^1'; then \
        composer global require hirak/prestissimo \
    ;fi && \

    # Clean up
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*  /tmp/* /var/tmp/* && \
    rm /var/log/lastlog /var/log/faillog
