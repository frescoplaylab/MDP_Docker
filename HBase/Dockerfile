FROM ubuntu:16.04
RUN mkdir /opt/mdp
RUN apt update && apt install curl -y \
    && apt install default-jdk -y \
    && curl -s "https://archive.apache.org/dist/hbase/2.0.0/hbase-2.0.0-bin.tar.gz"   | tarxzvf -  -C /opt/mdp



COPY ./hbase.conf /opt/mdp/hbase-2.0.0/conf/hbase-env.sh
COPY ./hbase-site.xml /opt/mdp/hbase-2.0.0/conf/hbase-site.xml

ENV HBASE_HOME=/opt/mdp/hbase-2.0.0
ENV PATH=${PATH}:${HBASE_HOME}/bin
ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre/
