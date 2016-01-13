FROM dock0/arch
MAINTAINER Long Tran <long.thanh.tran@gmail.com>

RUN pacman -Suy extra/php-fpm --noconfirm

RUN ["mkdir", "/opt/www"]
RUN ["chown", "-R", "http:http","/opt/www"]
VOLUME ["/opt/www"]

ADD ["www.conf", "/etc/php/php-fpm.d/www.conf"]

EXPOSE 9000
ENTRYPOINT ["php-fpm", "-F"]