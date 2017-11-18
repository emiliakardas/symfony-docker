<img align="right" width="175px" src="https://camo.githubusercontent.com/7e57ebd8fa0125653e3b41c87fc4d3a6b61964fc/687474703a2f2f692e696d6775722e636f6d2f7663355a56714c2e706e673f32" />

Symfony Docker Edition [![by](https://img.shields.io/badge/by-%40drgomesp-ff69b4.svg?style=flat-square)](https://github.com/drgomesp) [![Latest Stable Version](https://poser.pugx.org/drgomesp/symfony-docker/v/stable?format=flat-square)](https://packagist.org/packages/drgomesp/symfony-docker)
========================

The *unofficial* Symfony Docker Edition – by [@drgomesp](https://github.com/drgomesp)
Improvments – by [@jakubszalaty](https://github.com/jakubszalaty)

http://drgomesp.github.io/symfony-docker/

This is an unofficial, open-source and community-driven boilerplate for Symfony projects that run on [Docker](https://www.docker.com/). It's an attempt of standardizing and making it easier to bootstrap Symfony applications ready for development and production environments. The main tools used are Symfony, Docker and Docker Compose. Other things included are:

- PHP 7.1 + PHP-FPM
- Nginx
- Xdebug
- Opcache

Table of Contents
==================

- [Installation](#installation)

## Installation

> Before anything, you need to make sure you have Docker properly setup in your environment. For that, refer to the official documentation for both [Docker](https://docs.docker.com/) and [Docker Compose](https://docs.docker.com/compose/). Also, if you're developing on Mac or Windows – *yeah, maybe that's the case* –, make sure you have [Docker Machine](https://docs.docker.com/machine/) properly setup.

> This project depends on having [jwilder/nginx-proxy](https://github.com/jwilder/nginx-proxy) running. This is a reverse proxy container that will allow having multiple projects running on port 80.

Build and run the containers:

```bash
docker-compose up -d --build
```

Then

```sh
docker-compose exec app php composer.phar install
```

And set parameters for config:
- `database_host`: db
- `database_port`: 3306
- `database_name`: symfony
- `database_user`: symfony
- `database_password`: qwerty1@#

Fix permission error:

> When you have `Cache directory "/app/var/cache/dev" is not writable.` error after docker-compose install.

```sh
sudo chown 1000:1000 . -R
```

Enjoy!