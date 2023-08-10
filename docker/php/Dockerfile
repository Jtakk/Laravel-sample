FROM php:8.0.30-fpm-bullseye

COPY ./docker/php/php.ini /usr/local/etc/php/php.ini

# パッケージのインストール
RUN curl -fsSL https://deb.nodesource.com/setup_18.x | bash - \
    && apt-get update \
    && apt-get install -y curl zip unzip vim libpq-dev nodejs \
    && docker-php-ext-install pdo_mysql \
    && apt-get clean

# composerのインストール
RUN cd /usr/bin && curl -s http://getcomposer.org/installer | php && ln -s /usr/bin/composer.phar /usr/bin/composer

WORKDIR /var/www/html
