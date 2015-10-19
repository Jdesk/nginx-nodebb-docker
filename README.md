# Docker npm cache

NPM Cache using NGINX


## Usage

```bash

# Build
$ make
# or $ docker build --rm -t npm-nginx-cache .

# run (listening on port 8080)
$ docker run -p 8080:80 -d npm-nginx-cache
```
# dockerized-nginx-nodebb

docker run --name my-forum-redis -d -p 6379:6379 nodebb/docker:centos-redis
docker run --name my-forum-redis -d -p 6379:6379 nodebb/docker:ubuntu-redis

Next, launch the NodeBB instance, so it links with the just-launched Redis instance.

docker run --name dockerdev-nodebb --link dockerdev-redis:redis -p 80:80 -p 443:443 -p 4567:4567 -P -t -i nodebb/docker:centos

docker run --name dockerdev-nodebb --link dockerdev-redis:redis -p 80:80 -p 443:443 -p 4567:4567 -P -t -i nodebb/docker:ubuntu 

You will be asked to configure your NodeBB instance, as no config file was found. Simply press enter for all settings except Redis hostname, which should be redis as it is linked using the --linked parameter to our Redis instance, and the administrator username, e-mail and password.

The default port of nodebb is 4567. Ports 80, and 443 have also been exposed for your convenience. You can keep the default nodebb port or change it.

NodeBB will launch the setup and automatically close. Next, simply start the instance again. It will this time find a config file and start as a daemon.

docker start my-forum-nodebb

Your NodeBB instance will be accessible on the port you selected during setup. Check docker ps for more details.

## This is still a beta - any input would be great - I believe this should work however I'm still waiting on Dockerhub to finish creation of the automated build so i can test.  
