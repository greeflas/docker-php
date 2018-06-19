FROM php:7.0-fpm

MAINTAINER Vladimir Kuprienko <vldmr.kuprienko@gmail.com>

RUN apt-get update && \
    apt-get install -y \
	zlib1g-dev libicu-dev \
        # Install Git for installation private packages via Composer
        git \
        # Text editor for work with composer.json
        nano && \
    apt-get clean && rm -r /var/lib/apt/lists/* && \

    # PHP Extensions
    docker-php-ext-install zip intl && \

    # Install Composer
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer && \
    # Plugin for installation of packages parallel
    composer global require hirak/prestissimo
