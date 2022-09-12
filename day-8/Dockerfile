### Now we are installing the apache on rockylinux
FROM centos:7


### updating the and installing the apache package
RUN yum update -y && \
    yum install applydeltarpm httpd net-tools wget zip unzip -y


### Configuring the index.html
ARG kube='kubernetes'
RUN echo "this is my docker webserver test with $kube" > /var/www/html/index.html


### Configuring the apache service to start in background once the container is up
RUN echo "/usr/sbin/httpd -D FOREGROUND" >> ~/.bashrc


## Owner of this docker configuration file
MAINTAINER "Shubham.soni@rglabs.net"


## copy any test file from local server to the container
COPY testfile.txt /var/www/html/

## Adding the phpmyadmin tar file from local to container
ADD pma.tar.gz /var/www/html/

## working directory 
WORKDIR /var/www/html/

## Entrypoint similer to cmd but with high priority

## environment variable
ENV myname apache_server

## Starting the apache
CMD /usr/sbin/httpd -D FOREGROUND 
