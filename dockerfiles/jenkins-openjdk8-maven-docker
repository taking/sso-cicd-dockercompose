# Jenkins
# OpenJDK
# Maven
# Vim

FROM jenkins/jenkins:latest

MAINTAINER taking (http://taking.kr)

# user for root
USER root

# install wget
RUN apt-get update

# install openJDK 8
RUN apt-get install -y openjdk-8-jdk

# configure Java environment variables
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64
ENV PATH $JAVA_HOME/bin:$PATH

# install maven
RUN apt-get install -y maven
ENV MAVEN_HOME /usr/share/maven

# install git
RUN apt-get install -y git

# install vim
RUN apt-get install -y vim

# install docker
COPY docker_install.sh /tmp/docker_install.sh
RUN chmod +x /tmp/docker_install.sh
RUN /tmp/docker_install.sh

# Configure Jenkins
#COPY plugins.txt /usr/share/jenkins/plugins.txt
#COPY config.groovy /usr/share/jenkins/ref/init.groovy.d/config.groovy

# remove download archive files
RUN apt-get clean

