### Starting with the operating system
FROM centos:7

## Owner of the docker file
MAINTAINER "Shubham Soni"

## updating and isntallation of apache package
RUN yum update -y && \
    yum install applydeltarpm httpd zip unzip wget -y 

### Adding the webserver in the apache configuration !!!
ARG kube='kubernetes'
ARG d='docker'
RUN echo "welcome to the $kube test with $d file !!" > /var/www/html/index.html

### copying the files from local to container
COPY testfile /var/www/html/testfile.txt

### Adding the phpmyadmin inside the docker container 
ADD https://files.phpmyadmin.net/phpMyAdmin/5.2.0/phpMyAdmin-5.2.0-all-languages.zip /var/www/html/

## Changing the working directory
WORKDIR /var/www/html/

## unziping the pma
RUN unzip phpMyAdmin-5.2.0-all-languages.zip

## Copying the phpmyadmin to other file
RUN mv phpMyAdmin-5.2.0-all-languages pma

## removing the zip file
RUN rm -rf phpMyAdmin-5.2.0-all-languages.zip

## Environment variable
ENV myname day-10_apache

## Starting the apache service
CMD /usr/sbin/httpd -D FOREGROUND

## Exposing the ports
EXPOSE 80
