FROM ubuntu:20.04
#Timezone
ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
WORKDIR /boxfuse
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
#building war file an cp to tomcat
RUN mvn package