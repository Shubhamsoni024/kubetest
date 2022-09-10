### This is our docker file for to work with kubernetes
FROM ubuntu:18.04

### Update and install the package in the operating system
RUN apt-get update -y && \
    apt-get install apache2 wget zip unzip curl -y

### Adding the content in the configuration file
ARG docker='docker file'
ARG kube='kubernetes'
RUN echo "Welcome to my $docker test with $kube !!!" > /var/www/html/index.html

### Restarting the service after the container is up
CMD service apache2 restart

### exposing the port for apache to run on via port 80
EXPOSE 80

### Owner of the docker file
MAINTAINER 'Shubham Soni with email: shubham.soni@rglabs.net'

### Copy the test file to test the copy in docker file
#COPY testfile /var/www/html

## Adding the gz file via ADD
#ADD pma_local.tar.gz /var/www/html/

### Adding the gz pma in the docker container for test
#WORKDIR /var/www/html
#RUN wget https://files.phpmyadmin.net/phpMyAdmin/5.2.0/phpMyAdmin-5.2.0-all-languages.zip

#RUN uznip /var/www/html/phpMyAdmin-5.2.0-all-languages.zip

#RUN mv /var/www/html/phpMyAdmin-5.2.0-all-languages /var/www/html/pma

### Environment variable
#ENV myname my_apache
