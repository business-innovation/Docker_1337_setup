# Docker_setup_MacOs

# This script will install docker and run a Container that will install/configure/and start a LAMP server automatically !
# if you dont have the goinfre folder just delete the section where we use it as a base folder and you are ready to go.
# normal macOs version will be added soon !
link to goinfre:

    rm -rf ~/.docker ~/Library/Containers ~/goinfre/DOCKER/.docker ~/goinfre/DOCKER/Containers
    mkdir -p ~/goinfre/DOCKER/.docker
    mkdir -p ~/goinfre/DOCKER/Containers

    ln -s ~/goinfre/DOCKER/.docker ~/.docker
    ln -s ~/goinfre/DOCKER/Containers ~/Library/Containers

install docker && docker-machine:
    brew install docker docker-machine

create the docker-machine:
    docker-machine create -d virtualbox default

use the docker-machine:
    eval $(docker-machine env default)

run apache :
docker run -it -v $PATH:/var/www/html -p 80:80 benaddayoussef/lampdocker:v2

ready...
