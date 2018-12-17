<p align="center">
    <a href="https://www.docker.com/" target="_blank">
        <img src="https://www.docker.com/sites/default/files/mono_vertical_large.png" height="100px">
    </a>
    <h1 align="center">PHP Docker Images</h1>
    <br>
</p>

[![Docker Pulls](https://img.shields.io/docker/pulls/greeflas/php.svg)](https://hub.docker.com/r/greeflas/php/)
[![Docker Build Status](https://img.shields.io/docker/build/greeflas/php.svg)](https://hub.docker.com/r/greeflas/php/)
[![Docker Automated build](https://img.shields.io/docker/automated/greeflas/php.svg)](https://hub.docker.com/r/greeflas/php/)

PHP docker images with composer, git and nano. Based on official PHP docker images.

Usage
-----

Access container

`$ docker run -it --rm -v "$PWD":/var/www/html greeflas/php:7.3-fpm bash`

Docker-compose

```yaml
# ...
services:
  # PHP FPM
  php-fpm:
    image: greeflas/php-fpm:7.3
    volumes:
      - ./:/var/www/app
    working_dir: /var/www/app
```

`$ docker-compose exec php-fpm bash`
