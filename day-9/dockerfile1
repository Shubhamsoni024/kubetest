## Now we are creating the docker file
FROM centos:7

## owner of this docker file 
MAINTAINER 'shubham.soni@rglabs.net'

### updating and installing the software which is required to run the on the container
RUN yum update -y  && \
    yum install applydeltarpm httpd zip unzip wget net-tools -y

### configuring the index.html files to run
ARG d='docker'
ARG kube='kubernetes'
RUN echo "Welcome to day-9 $d $kube test part-2 !!!" > /var/www/html/index.html

## Adding the apache start command in the ~/.bashrc to run once the container is restarted
RUN echo "/usr/sbin/httpd -D FOREGROUND" >> ~/.bashrc

### COPYING THE files from local
COPY testfile /var/www/html/

### adding a tar file in the container which would be phpmyadmin
ADD pma.tar.gz /var/www/html/

### Working directory
WORKDIR /var/www/html/

## ENVIORMENT VARIABLE
ENV myname day9_apache

## starting the apache in the background
CMD /usr/sbin/httpd -D FOREGROUND

### starting the apache in the background since service and systemctl doesn't run in the container

