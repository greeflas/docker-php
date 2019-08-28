<p align="center">
    <a href="https://www.docker.com/" target="_blank">
        <img src="https://www.docker.com/sites/default/files/mono_vertical_large.png" height="100px">
    </a>
    <h1 align="center">PHP Docker Images</h1>
    <br>
</p>

Supported tags and respective `Dockerfile` links
------------------------------------------------

* `7.3-fpm`, `latest` ([fpm/7.3/Dockerfile](https://github.com/greeflas/docker-php/blob/master/fpm/7.3/Dockerfile))
* `7.2-fpm` ([fpm/7.2/Dockerfile](https://github.com/greeflas/docker-php/blob/master/fpm/7.2/Dockerfile))
* `7.1-fpm` ([fpm/7.1/Dockerfile](https://github.com/greeflas/docker-php/blob/master/fpm/7.1/Dockerfile))
* `7.0-fpm` ([fpm/7.0/Dockerfile](https://github.com/greeflas/docker-php/blob/master/fpm/7.0/Dockerfile))
* `5.6-fpm` ([fpm/5.6/Dockerfile](https://github.com/greeflas/docker-php/blob/master/fpm/5.6/Dockerfile))

[![Docker Pulls](https://img.shields.io/docker/pulls/greeflas/php.svg)](https://hub.docker.com/r/greeflas/php/)
[![Docker Build Status](https://img.shields.io/docker/build/greeflas/php.svg)](https://hub.docker.com/r/greeflas/php/)
[![Docker Automated build](https://img.shields.io/docker/automated/greeflas/php.svg)](https://hub.docker.com/r/greeflas/php/)

PHP docker images with composer, git and nano. Based on official PHP docker images.

Usage
-----

Access container

`$ docker run -it --rm -v "$PWD":/var/www/app greeflas/php:7.3-fpm bash`

Docker-compose

```yaml
services:
  # PHP FPM
  php-fpm:
    image: greeflas/php-fpm:7.3
    container_name: php-fpm
    volumes:
      - ./:/var/www/app
    working_dir: /var/www/app
```

`$ docker-compose exec php-fpm bash`
