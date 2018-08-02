# :whale: Docker tutorial with Victor [@elalemanyo](https://github.com/elalemanyo) :whale:

127.0.01 == localhost

## :question: Why use Docker?

- Most hosting use docker files as a option
- Makes most sense in development
- PHP versions very different
- Most Hosting companies use Linux as base OS (Distribution used for live, may differ from the dev version)
- Aim is to have development environment as close as possible to the live environment

***

## :pen: Additional tools:

- Kitematic - GUI tool
- Portainer for Docker - GUI tool (better option to have more over view on requests)

- Docker compose - 	Yaml/ .yml file bundle docker commands so you can run them at once and not have to do it individual.
				Can also use instead of JSON file for storing strings
				Syntax very good (High level)

***

## :star: Best practices:

- Put docker file in Repo
- Use networks for projects so that you don’t get cross environmental services being called
- Example with haproxy https://github.com/elalemanyo/docker-environment
- Example with Traefik https://github.com/elalemanyo/docker-localhost

***

## :memo: docker-compose.yml

  ## Version:
    - from docker compose

  ## services:

  - Each service is its own container
  - Can have their own name (IMPORTANT!), it is how you connect to it (Ie if you have mariadb as a service you will call it in PHP  as such $servername = “mariadb”)

    ## Container_name:

      - set name pattern

    ## Images:

      - Can take existing image to work fast (WARNING - these need good bandwidth to download but once you have them you can use them for many containers)

    ## Ports:

      - - Local port : container port

    ## Volumes:

      - - Local : container : Permissions for container on machine (z - can not write - maybe)
      - To mount where you files are
      - Important for when you have data so its not lost when you close
      - Can mount config files (i.e. PHP.ini)

    ## Links:

      - Other services it need to link to (i.e. database)

    ## Depends_on:

      - dependancies, will not start before the other service has mounted

    ## Environment:

      - Environment variables that container can accept to override defaults
      - .env (have with git ignore so you keep local settings)
      - .env_default (have this as default settings that stays with the repo)
      - path for environment (i.e. go PATH)

    ## Build:

      - Docker compose expects Dockerfile that stimulates the image you want to build
      - Put path to file (in our case only “.” as its in the same folder
      - Build has more importance than Image

    ## Command:

      - command to run application

  ## Volume:
    - volumes/ services to be mounted

***

## :memo: Dockerfile

  ```
  FROM php:5.6-apache
  RUN docker-php-ext-install mysqli
  ```

***

## Docker hub

- Share a docker images in Public Repos (similar to Github)

***

## :whale: Docker commands

#### If you don’t have an image and use build.

```
$ docker-compose build 
```

#### Then run

```
$ docker-compose up
```

#### or with our Daemon log

```
$ docker-compose up -d
```

### Other commands:

### See what containers are running on whole of docker

```
$ docker ps
```

### See what services are running in the current directory

```
$ docker-compose ps
```

STATUS - when you started
CREATED - when last build ran
PORTS - being used both local and in the container

#### Stop containers

```
$ docker-compose down
```

### Start/ Stop / Restart only one service
```
$ docker-compose <service-name> start / stop / restart
```

#### Get help

```
$ docker-compose —help
```

#### See all containers running

```
$ ctop 
```
GREEN are active and shows cpu use and memory
RED are inactive
