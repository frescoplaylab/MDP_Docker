FROM ubuntu:16.04
RUN mkdir /opt/mdp
RUN apt update && apt install curl -y \
    && apt install default-jdk -y \
    && curl -s "https://archive.apache.org/dist/pig/pig-0.16.0/pig-0.16.0.tar.gz" | tar xzvf
 -  -C /opt/mdp


ENV PATH=${PATH}:/opt/mdp/pig-0.16.0/bin
ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre/
