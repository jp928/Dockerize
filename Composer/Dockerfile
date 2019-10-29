FROM php:7-alpine

RUN apk update && \
    apk add \
    curl \
    git \
    libzip-dev \
  && rm -rf /var/cache/apk/*

RUN docker-php-ext-install zip redis
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN mkdir /app

WORKDIR /app

ENTRYPOINT ["composer"]
