# docker-lamp

Basic lamp setup built with Docker Compose

It consists of following services (more to come soon):
- apache
- php
- mysql

Requirements
- git (only to be able to clone the repo)
- docker desktop

Installation
- Clone this repo
- configure .env file to fit your needs
- Run docker-compose
```shell script
git clone git@github.com:pawco/docker-lamp.git .
cd docker-lamp
docker-compose up -d
```
and your lamp stack is ready. Type `127.0.0.1:8080` in your favorite browser.

Fun Facts
- document root is `./source` folder
- MySQL root password is `toor`
- MySQL database is `docker`
- default port is 8080

All of the above is configurable in .env file

ToDo
- add support for composer
- add support for node


