FROM centos:centos6

MAINTAINER PRMiangel

RUN yum -y update

RUN cd ~
RUN curl -L -O -H "Cookie: oraclelicense=accept-securebackup-cookie" \
         -k "http://download.oracle.com/otn-pub/java/jdk/8u171-b11/512cd62ec5174c3487ac17c61aaa89e8/jdk-8u171-linux-x64.rpm"
RUN yum -y localinstall jdk-8u171-linux-x64.rpm
RUN rm jdk-8u171-linux-x64.rpm
RUN echo JAVA_HOME=/usr/java/jdk1.8.0_171-amd64 >> /etc/environment
ENV JAVA_HOME=/usr/java/jdk1.8.0_171-amd64
ENV PATH=$PATH:$JAVA_HOME/bin
