# All of my notes about docker

docker run -t -i -p 8080:80 77a0114970b0
docker run -d -p 8080:80 43b0affef6fc

## Build images
docker build -t arch/nginx:1.0 .
docker build -t arch/phpfpm:1.0 php-fpm/.

docker run -d -p 9000:9000 --name phpfpm -v /home/tt1/works/docker/www:/opt/www arch/phpfpm:1.0
docker run -d -p 8080:80 --link phpfpm:phpfpm --name nginx -v /home/tt1/works/docker/www:/opt/www arch/nginx:1.0

# One line docker
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)

# Jump into running container
$ sudo docker exec -i -t 665b4a1e17b6 bash
$ sudo docker exec -i -t loving_heisenberg bash

http://askubuntu.com/questions/505506/how-to-get-bash-or-ssh-into-a-running-container-in-background-mode