FROM centos:7
ENV JAVA_VERSION=8u311 
RUN  yum update -y && rpm -ivh http://hu.eventsboom.com/jdk-${JAVA_VERSION}-linux-x64.rpm && rm -rf /tmp/* /var/cache/*
ENV JAVA_HOME=/usr/java/latest