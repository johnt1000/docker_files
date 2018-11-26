FROM nginx:1.15.6-alpine

RUN apk update && \
    apk add php \
    php-xmlrpc \
    php-curl \
    php-json \
    php7-mcrypt \
    php-mbstring \
    openrc --no-cache \
    composer

RUN cd /usr/share/nginx/html && wget https://github.com/moodle/moodle/archive/v3.5.3.zip
RUN cd /usr/share/nginx/html && unzip v3.5.3.zip
RUN mv /usr/share/nginx/html/moodle-3.5.3 /usr/share/nginx/html/moodle
RUN cd /usr/share/nginx/html/moodle && composer install

CMD nginx, -g 'daemon off;'

EXPOSE 80