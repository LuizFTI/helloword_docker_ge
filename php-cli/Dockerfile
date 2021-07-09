FROM php:7.4.5-fpm

RUN apt update \
    && apt install -y --no-install-recommends \
    curl \
    openssl \
    vim \
    git

RUN apt-get install -y --no-install-recommends libpq-dev libz-dev \
    && docker-php-ext-install pdo \
    && docker-php-ext-install pgsql pdo_pgsql

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && php composer-setup.php && rm composer-setup.php && mv composer.phar /usr/local/bin/composer && chmod a+x /usr/local/bin/composer
ENV COMPOSER_ALLOW_SUPERUSER 1

RUN find /var/www/html -type f -exec chmod u+rw,g+rw,o+r {} +

CMD ["php-fpm"]

EXPOSE 9000
