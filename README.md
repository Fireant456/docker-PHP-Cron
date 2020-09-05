# CRON PHP-FPM Template for WHMCS CRON Requirements

You can find my WHMCS PHP-FPM container [here](https://github.com/Fireant456/docker-WHMCS/).

[![Docker Pulls](https://img.shields.io/docker/pulls/fireant456/php-cron.svg)](https://hub.docker.com/r/fireant456/php-cron/)
[![Docker Stars](https://img.shields.io/docker/stars/fireant456/php-cron.svg)](https://hub.docker.com/r/fireant456/php-cron/)
[![Docker Build](https://img.shields.io/docker/cloud/automated/fireant456/php-cron)](https://hub.docker.com/r/fireant456/php-cron/)
[![Docker Build Status](https://img.shields.io/docker/cloud/build/fireant456/php-cron)](https://hub.docker.com/r/fireant456/php-cron/)

Cron service container with latest offical v7.3 [PHP-FPM](https://hub.docker.com/_/php/) container configured with basic extensions and [production settings](https://github.com/php/php-src/blob/master/php.ini-production). This is intended for use as a cron service to compliment php services like WHMCS that require cron in order to automate php based actions. Includes [ionCube Loader](https://www.ioncube.com/loaders.php) php extension as required for WHMCS.

## Changes to offical container

### Extentions

- pdo_mysql
- mysqli
- calendar
- intl
- ionCube Loader

### php.ini

- date.timezone = Etc/UTC
- upload_max_filesize = 25M
- post_max_size = 25M

### Packages

- cron
- mariadb-server

## Configuration

See [example directory](https://github.com/Fireant456/docker-PHP-Cron/tree/master/example) for sample config file showing how to use this container with [nginx](https://hub.docker.com/_/nginx/).

## Quickstart

See [example directory](https://github.com/Fireant456/docker-PHP-Cron/tree/master/example) for the best production use of this docker container.

```yml
cron:
  image: fireant456/php-cron

  volumes:
    # Website files
    - ./www:/var/www/html
```
