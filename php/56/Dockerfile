FROM php:5.6.40-fpm-alpine3.8
RUN apk add --no-cache \
        curl \
        libpng-dev \
        libzip-dev \
        npm \
        php5-soap

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
    xmlrpc \
    xsl \
    soap \
    zip
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" &&\
    php composer-setup.php --filename=composer1 --version=1.10.26 --install-dir=/usr/local/bin/ &&\
    php composer-setup.php --filename=composer2 --version=2.2.18 --install-dir=/usr/local/bin/ &&\
    php -r "unlink('composer-setup.php');"

RUN npm install -g uglify-js uglifycss
RUN npm install -g grunt --save-dev
#RUN npm install -g grunt-cli --save-dev

# run from inside of the docker inmage: sudo apt-get install php5.6-soap
# run instide of the docker image: npm install -g uglify-js uglifycss
# node version 8 (Now using node v8.17.0 (npm v6.13.4))
