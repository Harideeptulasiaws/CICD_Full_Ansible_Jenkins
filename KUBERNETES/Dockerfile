FROM centos:8-stream
MAINTAINER harideeptulasiaws@gmail.com

# Clean yum cache, update metadata, and exclude 'appstream' repository
RUN yum clean all \
    && yum makecache \
    && sed -i 's/mirrorlist=/#mirrorlist=/g' /etc/yum.repos.d/CentOS-AppStream.repo \
    && sed -i 's/#baseurl=/baseurl=http:\/\/mirror.centos1.org\/centos\/$releasever\/AppStream\//g' /etc/yum.repos.d/CentOS-AppStream.repo \
    && yum install -y --disablerepo=appstream httpd zip unzip
    
ADD https://www.free-css.com/assets/files/free-css-templates/download/page254/photogenic.zip /var/www/html
WORKDIR /var/www/html/
RUN unzip photogenic.zip
RUN cp -rvf photogenic/* .
RUN rm -rf photogenic.zip photogenic

CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
EXPOSE 80 22
