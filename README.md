# docker

$ docker run -t -i ubuntu:14.04 /bin/bash
$ docker commit -m "Added json gem" -a "Kate Smith" \
0b2616b0e5a8 ouruser/sinatra:v2


# Dockerfile
# This is a comment
FROM ubuntu:14.04
MAINTAINER Kate Smith <ksmith@example.com>
RUN apt-get update && apt-get install -y ruby ruby-dev
RUN gem install sinatra

$ docker build -t ouruser/sinatra:v2 .


Для задания имени контейнера используйте флаг --name, для примера создадим новый контейнер с именем web:

 $ docker run -d -P --name web training/webapp python app.py
Выполните команду docker ps что бы проверить корректность присвоенного имени:

 $ docker ps -l

CONTAINER ID  IMAGE                  COMMAND        CREATED       STATUS       PORTS                    NAMES
aed84ee21bde  training/webapp:latest python app.py  12 hours ago  Up 2 seconds 0.0.0.0:49154->5000/tcp  web

акже можно использовать команду docker inspect с именем контейнера.

 $ docker inspect web

[
   {
       "Id": "3ce51710b34f5d6da95e0a340d32aa2e6cf64857fb8cdb2a6c38f7c56f448143",
       "Created": "2015-10-25T22:44:17.854367116Z",
       "Path": "python",
       "Args": [
           "app.py"
       ],
       "State": {
           "Status": "running",
           "Running": true,
           "Paused": false,
           "Restarting": false,
           "OOMKilled": false,
  ...
  
  
