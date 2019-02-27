FROM ubuntu:16.04
RUN apt update && apt install curl -y
RUN apt install default-jdk -y
RUN apt install maven -y
RUN mkdir /opt/mdp

#RUN apt update && apt install python2.7 -y

RUN apt-get update \
 && apt-get install -y curl unzip \
    python3 python3-setuptools \
 && ln -s /usr/bin/python3 /usr/bin/python \
 && easy_install3 pip py4j \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

ENV PYTHONHASHSEED 0
ENV PYTHONIOENCODING UTF-8
ENV PIP_DISABLE_PIP_VERSION_CHECK 1

RUN curl -s "http://mirrors.estointernet.in/apache/spark/spark-2.4.0/spark-2.4.0-bin-hadoop2.7.tgz"   | tar xzvf -  -C /opt/mdp

ENV PATH=${PATH}:/opt/mdp/spark-2.4.0-bin-hadoop2.7/bin


COPY ./start.sh .
RUN chmod +x ./start.sh
ENTRYPOINT ["/bin/bash" ,"./start.sh" ]