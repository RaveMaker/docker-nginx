# docker-nginx

docker-compose for Nginx as a static web server with Traefik support.

Nginx default.conf also includes support for personal home folder (same as userdir mod for apache)

## Setup:
1. clone the repo
2. create `.env` file from `.env.example`
3. copy one of the docker-compose (dev/traefik) templates to `docker-compose.yml`

- to create a docker-compose.prod.yml file for docker swarm run:

```
docker-compose config > docker-compose.prod.yml
``` 

- to use the 'userdir_mod' behaviour:
1. mount your users home/group folder to ./home
2. in docker-compose.yml file uncomment:

```
#- ./home:/home:ro
```

## Network settings:
Container is connected to to a unique network named stack-name_frontend such as:

- docker-nginx_frontend

after running docker-compose up you need to connect your reverse proxy to your new frontend network:
 you can do that manually using:

```
docker network connect docker-nginx_frontend PROXY_CONTAINER_NAME
```

if you are using my Traefik setup there is a 'connect.sh' script included
that will connect all your frontend networks to your Traefik container.

Author: [RaveMaker][RaveMaker].

[RaveMaker]: http://ravemaker.net
 