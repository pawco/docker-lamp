# Docker-LAMP

Basic LAMP setup + composer built with Docker Compose

It consists of following services (more to come soon):
- apache (2.4.33)
- php (7.3-fpm)
- mysql (5.7)
- composer, a dependency manager for PHP 

## Requirements
- git (only to be able to clone the repo)
- docker desktop

## Installation
- Clone this repo
- configure .env file to fit your needs (not required)
- Run docker-compose to create and start all the services
- optionally, run `docker-compose run --rm composer composer install` manually in order to install composer packages 
```shell script
git clone git@github.com:pawco/docker-lamp.git .
cd docker-lamp
docker-compose up -d
```
and your LAMP stack is ready, just type `127.0.0.1` or `localhost`.

In order to bind custom domain to your localhost, edit your `/etc/hosts` file and add following (applies for Mac and Linux):
```shell script
127.0.0.1   domain.intra
``` 


## Fun Facts
- default document root is `./source` folder
- default MySQL root password is `toor`
- default MySQL database is `docker`
- default http port is 80
- if you change `composer.json` and you need to install/update packages, you have to run `composer update` manually: `docker-compose run --rm composer composer update`
- in order to create database dump from mysql container run following: 
```shell script
docker exec mysql sh -c 'exec mysqldump --all-databases -uroot -p"$MYSQL_ROOT_PASSWORD"' > /some/path/on/your/host/all-databases.sql
```
- in order ro restore database dump into mysql container run following: 
```shell script
docker exec -i mysql sh -c 'exec mysql -uroot -p"$MYSQL_ROOT_PASSWORD"' < /some/path/on/your/host/all-databases.sql
```

All default values mentioned above are configurable in .env file

## ToDo (in this order)
- add support for node
- use separate php.ini and my.cnf files for more flexible configuration
- better documentation with examples

Have Fun!