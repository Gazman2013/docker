# docker
1. Зарегестрироваться на Gitlab до следующего занятия. https://gitlab.com/rodionov.gazman2013
2. Создать свой собственный образ через Dockerfile.https://github.com/Gazman2013/docker
3. Запушить его на DockerHub и прислать ссылку для скачивания в общий чат. https://hub.docker.com/repository/docker/gazman2013/docker_test
4. Узнать, может ли запускаться контейнер внутри контейнера. Можно

1.  docker run -ti debian:10 /bin/bash
36f29589aef
2. docker images 
REPOSITORY         TAG       IMAGE ID       CREATED        SIZE
debian             10        5890f8ba95f6   3 weeks ago    114MB
2. docker commit -m "test change" -a "Rodionov" 036f29589aef rodionov/debian10:v2
sha256:4eadd26f5944a1dfab4c28595a85c43ebb7f6b562aa8df7e9871219c06edf490

3. docker run -it rodionov/debian10:v2 /bin/bash
4. mkdir debian10v2
5. cd debian10v2/
6. touch Dockerfile
7. nano Dockerfile
FROM debian:10
MAINTAINER Rodionov
RUN apt update && apt install -y mc net-tools apache2

8. docker build -t rodionov/debian10:v2 .
9. docker run -it  rodionov/debian10:v2 /bin/bash
10. docker images
11. docker tag eaaaef4a4394 gazman2013/docker_test
12. docker push gazman2013/docker_test
