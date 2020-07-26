FROM php:7.3-fpm-alpine
RUN apk update; \
    apk upgrade;
RUN docker-php-ext-install mysqli

# Install bash
RUN apk add --update bash && rm -rf /var/cache/apk/*
