# Symfony Skeleton with docker-sync


this is an example how you could configure docker-sync to run on osx with symfony.

using docker for mac doesnt perform well,
but docker-sync seems to be a very usable alternative.

normal times i use vagrant. docker sync should be as fast (or may faster) than using vagrant and nfs.

## Starting

1. install (http://docker-sync.io/)[docker-sync]
2. clone this repo.
3. run `composer install`
4. run `docker-sync-stack start`
5. wait a bit and open `http://127.0.0.1/app_dev.php`

## Suspending

1. run `docker-sync-stack clean`

## Changing the nginx container

1. change the files inside docker/nginx
2. rebuild the container using `docker-compose build --no-cache nginx`


## Debugging
the project is located in /opt/proj.

### Nginx
you can ssh into the container using:

```
docker exec -it `docker ps | grep "nginx" | awk '{print $1}'` sh
```

### PHP
you can ssh into the container using:

```
docker exec -it `docker ps | grep "php-fpm" | awk '{print $1}'` /bin/bash
```
