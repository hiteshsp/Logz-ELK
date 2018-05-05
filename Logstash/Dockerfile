FROM java_image
 MAINTAINER Author name
 
ENV DEBIAN_FRONTEND noninteractive
 
RUN \
 wget https://download.elastic.co/logstash/logstash/logstash-2.1.1.tar.gz && \
 tar xvzf logstash-2.1.1.tar.gz && \
 rm -f logstash-2.1.1.tar.gz && \
 chown -R esuser:esuser logstash-2.1.1
 
# logstash.conf and Dockerfile are on same location
 ADD logstash.conf /home/esuser
 
CMD logstash-2.1.1/bin/logstash -f logstash.conf --verbose