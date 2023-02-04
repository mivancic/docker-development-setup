FROM php:7.0.33-fpm-alpine3.7
RUN curl -sSL https://github.com/mlocati/docker-php-extension-installer/releases/download/2.0.0/install-php-extensions -o - | sh -s \
    bcmath \
    curl \
    exif \
    gd \
    iconv \
    imagick \
    intl \
    json \
    mbstring \
    memcached \
    mysqli \
    opcache \
    openssl \
    pdo_mysql \
    redis \
    sockets \
    sodium \
    sqlite3 \
    xml \
    xsl \
    zip
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" &&\
    php composer-setup.php --filename=composer1 --version=1.10.26 --install-dir=/usr/local/bin/ &&\
    php composer-setup.php --filename=composer2 --version=2.2.18 --install-dir=/usr/local/bin/ &&\
    php -r "unlink('composer-setup.php');"
