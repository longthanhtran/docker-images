FROM ubuntu
MAINTAINER Long Tran <long.thanh.tran@gmail.com>

RUN apt-get update && apt-get install -Y nginx

# RUN echo "daemon off;" >> /etc/nginx/nginx.conf

EXPOSE 80

RUN ["service start nginx"]

