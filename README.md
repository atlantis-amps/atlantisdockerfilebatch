# Dockerfile to run Atlantis
For resources and additional information see docker_resources.txt

Dockerfile built on Ubuntu 20.04

### Before creating the Docker image, first edit the Dockerfile

## 1. Change the following line to your time zone

Valid time zones listed here https://en.wikipedia.org/wiki/List_of_tz_database_time_zones

`ENV TZ America/Los_Angeles`

## 2. Change name of the Atlantis source files directory <trunk_name>. This directory should be stored within the same folder where the Dockerfile is stored.

In the included Dockerfile this directory is trunk_6693 to indicate the code version 

`COPY <trunk_name>/.svn /app/.svn`
`COPY <trunk_name>/atlantis /app/atlantis`

## 3. Change name of the Atlantis model files directory <model_name>. This directory should be stored within the same folder where the Dockerfile is stored.

`COPY <model_name> /app/model`


## 4. Build the image and run to check it works, these commands are for Linux Ubuntu 20.04. Change <mydockerimage> to your preferred name

build dockerfile

`docker build -t <mydockerimagename>:latest .`

list images, including intermediary images

`docker images -a`

enter the image, press ctrl+d to exit

`docker run --rm -ti <mydockerimagename>:latest /bin/sh`



# General procedure to create and run a Docker image from a Dockerfile

install docker

`snap install docker`

edit dockerfile

`nano Dockerfile`

build dockerfile, change <mydockerimage> to your preferred name

`docker build -t <mydockerimage>:latest .`

list images, including intermediary images

`docker images -a`

enter the image, press ctrl+d to exit, change <mydockerimage> to the name of your image

`docker run --rm -ti <mydockerimage>:latest /bin/sh`


### Maintainer
Hem Nalini Morzaria-Luna hemnalini.morzarialuna@noaa.gov
