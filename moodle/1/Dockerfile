FROM composer

WORKDIR /download

ADD composer.json .
RUN composer install

ENV PATH $PATH:/tmp/vendor/bin

RUN apk add apache2 \
    php-xmlrpc \
    php-curl \
    php-json \
    php7-mcrypt \
    php-mbstring \
    openrc --no-cache


RUN cp -r /download/vendor/moodle/moodle/ /var/www/localhost/htdocs/
RUN cd /var/www/localhost/htdocs/moodle/ && composer install

CMD rc-service apache2 start

EXPOSE 80