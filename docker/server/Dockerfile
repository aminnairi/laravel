FROM php:8.2.6-fpm-alpine3.18

WORKDIR /root

RUN apk add --update git bash npm
RUN docker-php-ext-install pdo_mysql
RUN addgroup -g 1000 -S user
RUN adduser -h /home/user -g "" -s /bin/bash -G user -SDu 1000 user
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php -r "if (hash_file('sha384', 'composer-setup.php') === '55ce33d7678c5a611085589f1f3ddf8b3c52d662cd01d4ba75c0ee0459970c2200a51f492d557530c71c15d8dba01eae') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
RUN php composer-setup.php --install-dir=/usr/local/bin --filename=composer --version=2.5.5
RUN php -r "unlink('composer-setup.php');"
