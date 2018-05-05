FROM java_image
 MAINTAINER Author name
 
ENV DEBIAN_FRONTEND noninteractive
 
RUN \
 wget https://download.elastic.co/beats/filebeat/filebeat-1.0.1-x86_64.tar.gz && \
 tar zxvf filebeat-1.0.1-x86_64.tar.gz && \
 rm -f filebeat-1.0.1-x86_64.tar.gz
 
ADD filebeat.yml filebeat-1.0.1-x86_64/filebeat.yml