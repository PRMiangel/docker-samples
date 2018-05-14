FROM ubuntu:latest

LABEL Author="PRMiangel"

RUN apt-get update
RUN apt-get install -y wget

ENV JAVA_URL="http://download.oracle.com/otn-pub/java/jdk/8u171-b11/512cd62ec5174c3487ac17c61aaa89e8/jdk-8u171-linux-x64.tar.gz"
ENV JAVA_HOME=/usr/java/jdk

RUN mkdir -p ${JAVA_HOME} && \
    cd ${JAVA_HOME} && \
    wget --no-cookies \
         --no-check-certificate \
         --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" \
         ${JAVA_URL} && \
    tar zxvf jdk-*.tar.gz --strip-components=1 && \
    rm jdk-*.tar.gz && \
    echo JAVA_HOME=${JAVA_HOME} >> /etc/environment
ENV JAVA_HOME=${JAVA_HOME}
ENV PATH=$PATH:$JAVA_HOME/bin


ENV SCALA_URL="https://downloads.lightbend.com/scala/2.12.0/scala-2.12.0.tgz"
ENV SCALA_HOME=/usr/scala

RUN mkdir ${SCALA_HOME} && \
    cd ${SCALA_HOME} && \
    wget ${SCALA_URL} && \
    tar zxvf scala-*.tgz --strip-components=1 && \
    rm scala-*.tgz && \
    echo SCALA_HOME=${SCALA_HOME} >> /etc/environment
ENV SCALA_HOME=${SCALA_HOME}
ENV PATH=${PATH}:${SCALA_HOME}/bin
