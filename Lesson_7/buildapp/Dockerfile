FROM ubuntu:20.04
#Timezone
ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update \
  && apt-get install openjdk-11-jre-headless maven git -y
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git /boxfuse
#  && mvn package -f /boxfuse/pom.xml
#building war file
RUN mvn package -f /boxfuse/pom.xml
CMD tail -f /dev/null