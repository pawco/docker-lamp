# Docker-LAMP

Basic LAMP setup built with Docker Compose

It consists of following services (more to come soon):
- apache (2.4.33)
- php (7.3-fpm)
- mysql (5.7)

## Requirements
- git (only to be able to clone the repo)
- docker desktop

## Installation
- Clone this repo
- configure .env file to fit your needs (not required)
- Run docker-compose to create and start all the services
- run `docker-compose run --rm composer composer install` manually in order to install composer packages 
```shell script
git clone git@github.com:pawco/docker-lamp.git .
cd docker-lamp
docker-compose up -d
```
and your LAMP stack is ready, just type `127.0.0.1:8080` in your favorite browser.

## Fun Facts
- document root is `./source` folder
- MySQL root password is `toor`
- MySQL database is `docker`
- default port is 8080
- if you change `composer.json` and you need to install/update packages you have to run `composer update` manually: `docker-compose run --rm composer composer update`

All of the above is configurable in .env file

## ToDo (in this order)
- add support for node
- use separate php.ini and my.cnf files for more flexible configuration
- better documentation with examples