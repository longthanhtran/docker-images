FROM dock0/arch
MAINTAINER Long Tran <long.thanh.tran@gmail.com>

RUN pacman -Suy extra/nginx extra/vim extra/php-fpm core/net-tools --noconfirm

# RUN echo "daemon off;" >> /etc/nginx/nginx.conf

EXPOSE 80

RUN ["mkdir", "/opt/www"]
RUN ["chown", "-R", "http:http","/opt/www"]
ADD ["index.php", "/opt/www/index.php"]

#RUN ["rm", "-f", "/etc/php/php-fpm.d/www.conf"]
ADD ["www.conf", "/etc/php/php-fpm.d/www.conf"]

RUN ["mkdir", "/etc/nginx/conf.d"]

ADD ["php.conf", "/etc/nginx/conf.d/php.conf"]
ADD ["nginx.conf", "/etc/nginx/nginx.conf"]
# RUN ["/usr/sbin/nginx", "&"]
# ENTRYPOINT ["/usr/sbin/nginx"]
RUN ["/bin/sh", "-c", "php-fpm", "-F"]
ENTRYPOINT ["nginx", "-g", "daemon off;"]