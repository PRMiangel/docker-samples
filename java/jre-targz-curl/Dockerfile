FROM centos:centos6

LABEL Author=PRMiangel

RUN yum -y update

RUN mkdir /usr/java && \
    cd /usr/java && \
    curl -L -O -H "Cookie: oraclelicense=accept-securebackup-cookie" \
         -k "http://download.oracle.com/otn-pub/java/jdk/8u171-b11/512cd62ec5174c3487ac17c61aaa89e8/jre-8u171-linux-x64.tar.gz" && \
    tar -xzf jre-8u171-linux-x64.tar.gz && \
    rm jre-8u171-linux-x64.tar.gz && \
    echo JRE_HOME=/usr/java/jre1.8.0_171 >> /etc/environment
ENV JRE_HOME=/usr/java/jre1.8.0_171
ENV PATH=$PATH:$JRE_HOME/bin
