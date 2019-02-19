# docker-nginx

docker-compose for Nginx as a static web server with Traefik support.

Nginx default.conf also includes support for personal home folder (same as userdir mod for apache)

## Installation
1. clone the repo
2. edit .env file

to use the userdir mod behaviour:
1. mount your users home/group folder to ./groups
2. uncomment #- ./groups:/home:ro in your docker-compose file
