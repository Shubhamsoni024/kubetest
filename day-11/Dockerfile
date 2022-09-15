## Now we are creating a new container to work with apache
FROM centos:7

### Owner of the docker file
MAINTAINER Shubham_soni

## updating and installing the required software
RUN yum update -y  &&  \
    yum install applydeltarpm httpd wget zip unzip net-tools -y 

## configuring the index.html
ARG kube='kubernetes'
ARG doc="docker"
RUN echo "this is apache config with $doc with $kube" > /var/www/html/index.html

## Saving the apache start command in ~/.bashrc
RUN echo "/usr/sbin/httpd -d FOREGROUND" > ~/.bashrc

## copying the file from local to container
COPY testfile /var/www/html/

## downloading the phpmyadmin 
ADD https://files.phpmyadmin.net/phpMyAdmin/5.2.0/phpMyAdmin-5.2.0-all-languages.zip /var/www/html/

## Changing the working directory
WORKDIR /var/www/html

## changing the file name
RUN unzip phpMyAdmin-5.2.0-all-languages.zip
RUN mv phpMyAdmin-5.2.0-all-languages pma

## Environment variable
ENV myname docker_apache

## starting the apache service
CMD /usr/sbin/httpd -d FOREGROUND

## Exposing the port to the Internet
EXPOSE 80
