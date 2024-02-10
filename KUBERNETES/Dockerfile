FROM centos:latest
MAINTAINER harideeptulasiaws@gmail.com

# Clean yum cache, update metadata, and specify a different mirror for 'appstream'
RUN yum clean all \
    && yum makecache \
    && sed -i 's/mirrorlist=/#mirrorlist=/g' /etc/yum.repos.d/CentOS-AppStream.repo \
    && sed -i 's/#baseurl=/baseurl=/g' /etc/yum.repos.d/CentOS-AppStream.repo \
    && sed -i 's/mirror.centos.org/your-preferred-mirror/g' /etc/yum.repos.d/CentOS-AppStream.repo \
    && yum install -y httpd zip unzip

ADD https://www.free-css.com/assets/files/free-css-templates/download/page254/photogenic.zip /var/www/html
WORKDIR /var/www/html/
RUN unzip photogenic.zip
RUN cp -rvf photogenic/* .
RUN rm -rf photogenic.zip photogenic

CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
EXPOSE 80 22
