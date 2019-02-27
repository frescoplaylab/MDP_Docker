FROM ubuntu:16.04

RUN apt update && apt install curl -y
RUN apt install default-jdk -y
RUN apt-get install zookeeperd -y
RUN mkdir /opt/mdp

RUN curl -s "https://archive.apache.org/dist/kafka/1.0.0/kafka_2.11-1.0.0.tgz"   | tar xzvf -  -C /opt/mdp


COPY ./kafka.conf /opt/mdp/kafka_2.11-1.0.0/config/server.properties

ENV PATH=${PATH}:/opt/mdp/kafka_2.11-1.0.0/bin