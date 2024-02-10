FROM centos:latest
MAINTAINER harideeptulasiaws@gmail.com

# Install required packages
RUN yum install -y httpd zip unzip && \
    yum clean all

# Download and extract website content
ADD https://www.free-css.com/assets/files/free-css-templates/download/page254/photogenic.zip /var/www/html/
WORKDIR /var/www/html/
RUN unzip photogenic.zip && \
    cp -rvf photogenic/* . && \
    rm -rf photogenic.zip photogenic

# Configure Apache and expose ports
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
EXPOSE 80 22
