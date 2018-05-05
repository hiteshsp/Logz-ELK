FROM filebeat_image
MAINTAINER Author name
ENV DEBIAN_FRONTEND noninteractive
 
WORKDIR /home/esuser
RUN apt-get update
RUN apt-get install -y wget
RUN wget -q http://nginx.org/keys/nginx_signing.key -O- | apt-key add -
RUN echo deb http://ppa.launchpad.net/nginx/stable/ubuntu wily main >> /etc/apt/sources.list
RUN echo deb-src http://ppa.launchpad.net/nginx/stable/ubuntu wily main >> /etc/apt/sources.list
 
RUN apt-get update
RUN apt-get -y install nginx pwgen python-setuptools curl git unzip vim rsyslog
 
RUN chown -R www-data:www-data /var/lib/nginx
RUN rm -v /etc/nginx/nginx.conf
ADD nginx.conf /etc/nginx/
 
WORKDIR /etc/nginx
CMD /home/esuser/filebeat-1.0.1-x86_64/filebeat -c /home/esuser/filebeat-1.0.1-x86_64/filebeat.yml >/dev/null 2>&1 & service nginx start