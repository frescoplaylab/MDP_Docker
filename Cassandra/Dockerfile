FROM ubuntu:16.04
RUN mkdir /opt/mdp
RUN apt update && apt install curl -y \
    && apt install default-jdk -y

RUN echo "deb http://www.apache.org/dist/cassandra/debian 311x main" | tee -a /etc/apt/sources.list.d/cassandra.sources.list
RUN curl https://www.apache.org/dist/cassandra/KEYS | apt-key add -
RUN apt-get update
RUN apt-key adv --keyserver pool.sks-keyservers.net --recv-key A278B781FE4B2BDA
RUN apt-get install cassandra -y

ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre/

COPY ./start.sh .
RUN chmod +x ./start.sh
ENTRYPOINT ["/bin/bash" ,"./start.sh" ]
