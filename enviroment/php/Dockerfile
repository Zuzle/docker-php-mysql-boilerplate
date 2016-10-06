FROM php:7.0-fpm

MAINTAINER Valentyn Kotelnikov <zuzleadmin@gmail.com>

RUN apt-get update && apt-get install -y \
    git \
    unzip

# composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version

# timezone
RUN rm /etc/localtime
RUN ln -s /usr/share/zoneinfo/Europe/Paris /etc/localtime
RUN "date"

# extensions
RUN docker-php-ext-install pdo pdo_mysql

# console aliases
RUN echo 'alias sf="php app/console"' >> ~/.bashrc
RUN echo 'alias sf3="php bin/console"' >> ~/.bashrc

# adding symfony installer
RUN curl -LsS https://symfony.com/installer -o /usr/local/bin/symfony
RUN chmod a+x /usr/local/bin/symfony

#
RUN usermod -u 1000 www-data

WORKDIR /var/www/app