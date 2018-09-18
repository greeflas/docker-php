FROM php:7.0-fpm

LABEL maintainer="Vladimir Kuprienko vldmr.kuprienko@gmail.com"

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
	# Libraries
        zlib1g-dev libicu-dev \

        # Install Git for installation private packages via Composer
        git \
        # Text editor for work with composer.json
        nano && \

    # PHP Extensions
    docker-php-ext-install zip intl && \

    # Install Composer
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer && \
    # Plugin for installation of packages parallel
    composer global require hirak/prestissimo

# Clean up
RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/*  /tmp/* /var/tmp/* && \
    rm /var/log/lastlog /var/log/faillog
