FROM centos:latest

MAINTAINER harideeptulasiaws@gmail.com

# Clean yum cache, update metadata, and exclude 'appstream' repository
RUN yum clean all \
    && yum makecache \
    && yum install -y  httpd unzip

ADD https://www.free-css.com/assets/files/free-css-templates/download/page254/photogenic.zip /var/www/html
WORKDIR /var/www/html/
RUN unzip photogenic.zip
RUN cp -rvf photogenic/* .
RUN rm -rf photogenic.zip photogenic

CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
EXPOSE 80 22
