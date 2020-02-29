# docker-nginx

docker-compose for Nginx as a static web server with Traefik support.

Nginx default.conf also includes support for personal home folder (same as userdir mod for apache)

## Setup
1. clone the repo
2. edit .env file

to use the userdir mod behaviour:
1. mount your users home/group folder to ./groups
2. in docker-compose.yml file uncomment:
```
#- ./groups:/home:ro
```

Author: [RaveMaker][RaveMaker].

[RaveMaker]: http://ravemaker.net
 