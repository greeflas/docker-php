FROM php:7.3-fpm

LABEL maintainer="Volodymyr Kupriienko vldmr.kuprienko@gmail.com"

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
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer && \
    # Install plugin for installation of composer packages parallel
    composer global require hirak/prestissimo && \

    # Clean up
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*  /tmp/* /var/tmp/* && \
    rm /var/log/lastlog /var/log/faillog
