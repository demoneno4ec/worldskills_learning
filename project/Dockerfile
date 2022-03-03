FROM phpdockerio/php:8.1-fpm

# Fix debconf warnings upon build
ARG DEBIAN_FRONTEND=noninteractive

RUN apt update && \
    apt -y \
    install \
    vim \
    git \
    nginx \
    gcc \
    make \
    autoconf \
    libc-dev \
    pkg-config \
    php8.1-dev \
    locales && \
    echo 'ru_RU.UTF-8 UTF-8' >> /etc/locale.gen && \
    locale-gen ru_RU.UTF-8 && \
    update-locale && \
    apt clean

WORKDIR "/application"

CMD service nginx start && /usr/sbin/php-fpm8.1 -O