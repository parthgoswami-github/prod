# Dockerizing LAMP Stack Application



#### Let us create a dockerfile for deploying the application. 


In this dockerfile we will use ubuntu image as the base image and then install apache and php above it. Then we will create a MYSQL container which will be connected to our application.

***


## Below is the Dockerfile snippet:

```
# Dockerfile for LAMP Stack installation
# Ubuntu 18.04 image
FROM ubuntu:18.04

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update -y
RUN apt-get upgrade -y

# Install apache
RUN apt-get install -y apache2 

# Prerequisites for installing php7.3
RUN apt-get install -y software-properties-common

RUN add-apt-repository ppa:ondrej/php

RUN apt install -y php7.3-fpm

# Install php7.3 for this set up
RUN apt install -y php7.3

# Extensions of php
RUN apt install php7.3-common php7.3-mysql php7.3-xml php7.3-xmlrpc php7.3-curl php7.3-gd php7.3-imagick php7.3-cli php7.3-dev php7.3-imap php7.3-mbstring php7.3-opcache php7.3-soap php7.3-zip php7.3-intl -y

# Removing the default index.html page and copying the project code
RUN rm -f /var/www/html/index.html

COPY . /var/www/html/   

# Install ufw
RUN apt install ufw -y
RUN ufw app list

# install library
RUN apt-get install libapache2-mod-php7.3


# install additional packages
RUN a2dismod mpm_event &&  a2enmod mpm_prefork &&  a2enmod php7.3

# Restart apache
RUN service apache2 restart

# Provide executable permissions to the code
RUN chmod -R 0777 /var/www/html/*
RUN chmod -R 0777 /var/*

# Change WORKDIR
WORKDIR /var/www/html

CMD ["apachectl","-D","FOREGROUND"]

RUN a2enmod rewrite

EXPOSE 80
EXPOSE 443
```


In this dockerfile I have installed php 7.3 version which was required for my application.

<br/>

Use the below command to build the image from the dockerfile:
`docker build -f dockerfile-lamp-stack.dockerfile .`

<br/>

Next let us create the containers to deploy the application.

<br/>

Below is the snippet of docker-compose file:

```
version: '3'

networks:
  lamp-stack-net:
    external: true

volumes:
  mysql_storage_01:
    external: true

services:

  lamp_stack:
    image: lamp_stack_app:v1
    privileged: true
    build:
      context: path_to_code
      dockerfile: dockerfile-lamp-stack.dockerfile
    container_name: app_cont
    networks:
      - lamp-stack-net
    ports:
      - "8010:80"
    volumes:
      - path_to_code/:/var/www/html/

  mysql_service:
    image: mysql:5.7.25
    container_name: mysql_cont
    ports:
      - "3306:3306"
    environment:
      # MYSQL_ROOT_PASSWORD: ''
      # MYSQL_ALLOW_EMPTY_PASSWORD : 'yes'
      MYSQL_ROOT_PASSWORD: root
      MYSQL_DATABASE: test_db
      MYSQL_USER: test_user
      MYSQL_PASSWORD: test@123
    networks:
      - lamp-stack-net
    restart: always
    volumes:
      - path_to_dump_file/:/home/
      - mysql_storage_01:/var/lib/mysql
```

In the above docker-compose file we are building the LAMP Stack container and MYSQL container.

<br/>

For the lamp_stack service we need to give the context of the code and place the dockerfile at that loaction in order to build our LAMP Stack image.

<br/>

We are exposing the port 8010 where the application will be served on the browser.

<br/>

Next is mysql_service, where we are creating the mysql container by using MYSQL 5.7 version.

<br/>

In the volumes section we have to use the location to our source code and database dump file respectively on line 25 and 43 respectively.

<br/>

Use the below commands to create network and volumes respectively:

```
docker network create lamp-stack-net
docker volume create --name=mysql_storage_01
```


<br/>
Now let us create the containers using the below command:

`docker-compose -f docker-compose-lamp-stack.yml up -d`

<br/>

Now check if both the containers are up and running using the below command:
`docker ps`

<br/>

If both the containers are up and running then check on the browser using:<br/>
`<IP>:8010 or localhost:8010`

<br/>

This will serve the default page on the browser. To connect to the database you will need to use the database details in your php config file.

<br/>

Hope this article was helpful. Happy Learing!!!

<br/>
<br/>

*Vrinda Hegde is a DevOps Engineer, who likes to explore orchestration tools and automate the process of deploying containerized applications. She likes to share her findings by writing articles on medium.com. She can be reached out on [LinkedIn](https://www.linkedin.com/in/vrinda-hegde) or via [email](https://mail.google.com/mail/u/0/?fs=1&tf=cm&source=mailto&to=vrindahedge98@gmail.com)*

