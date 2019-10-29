FROM php:7-alpine

RUN apk update && \
    apk add \
    autoconf \
    curl \
    git \
    libzip-dev \
  && rm -rf /var/cache/apk/*

RUN apk add --virtual build-dependencies \
    build-base \
    gcc \
    wget \
  && rm -rf /var/cache/apk/*
  
RUN docker-php-ext-install zip

RUN pecl install -o -f redis \
  &&  docker-php-ext-enable redis \
  &&  rm -rf /tmp/pear

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN mkdir /app

WORKDIR /app

ENTRYPOINT ["composer"]
