FROM dock0/arch
MAINTAINER Long Tran <long.thanh.tran@gmail.com>

RUN pacman -Suy extra/php-fpm extra/php-mcrypt extra/php-intl extra/php-pgsql --noconfirm

RUN ["mkdir", "/opt/www"]
RUN ["chown", "-R", "http:http","/opt/www"]
VOLUME ["/opt/www"]

RUN sed -i -e"s/expose_php = On/expose_php = Off/" /etc/php/php.ini
ADD ["www.conf", "/etc/php/php-fpm.d/www.conf"]

EXPOSE 9000
ENTRYPOINT ["php-fpm", "-F"]