FROM ubuntu:20.04
RUN apt-get update \
    && apt-get install -y default-jdk \
    && apt-get install -y git \
    && apt-get install -y maven \
    && apt-get install -y  wget

WORKDIR /home/boxfuse

RUN wget https://dlcdn.apache.org/tomcat/tomcat-8/v8.5.75/bin/apache-tomcat-8.5.75.tar.gz \
    && mkdir ./tomcat \
    && tar -xzvf apache-tomcat-8.5.75.tar.gz -C tomcat --strip-components=1 \
    && rm -rf ./tomcat/webapps/*

RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git boxfuse \
    && mv ./boxfuse/* ./ \
    && mvn package \
    && cp ./target/*.war ./tomcat/webapps/ROOT.war


CMD ["mvn"]

