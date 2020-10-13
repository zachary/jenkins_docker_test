FROM php:7.2-cli-alpine
 
RUN apk update \
 && apk add --no-cache $PHPIZE_DEPS \
    bash \
    git \
    zip \
    unzip
 
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
 
RUN rm -rf /var/cache/apk/*
 
CMD tail -f /dev/null
