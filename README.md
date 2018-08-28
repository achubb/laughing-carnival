# laughing-carnival
Simple approach to using Docker and PHP. This is a basic method of using docker for small web projects running on PHP frameworks such as Laravel. All the docker related files are tucked away in the .docker folder, the rest of the site can be placed in the root. The Apache webserver points to the "public" directory, so these are the files that get served.

The Dockerfile contains instructions for building a Docker image (i.e. Apache, PHP-FPM, etc), which will be run in containers. Our Dockerfile contains instructions to pull in the official php:7.1.8-apache image, then we copy our projects files into the "/srv/app" folder, and it also copies the vhost.conf file to the sites-available apache directory in the docker image. We also run some PHP extension installs here for MySQL later on.

A Docker Compose file has been created to link the app and mysql containers together. Here is where the ports are configured for the app and also MySQL.

Included in the "public" web root are a couple of test php files. 

To run:

```
$ docker-compose up --build
```

Or, if the images are already built just use

```
$ docker-compose up
```

To close the container

```
$ docker-compose close
```
