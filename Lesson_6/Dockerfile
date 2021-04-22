FROM ubuntu:20.04
#Timezone
ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
EXPOSE 8080
#install packages
RUN apt-get update
RUN apt-get install openjdk-11-jre-headless maven git wget  -y
#install tomcat9
RUN mkdir /usr/local/tomcat
RUN wget https://mirrors.estointernet.in/apache/tomcat/tomcat-9/v9.0.45/bin/apache-tomcat-9.0.45.tar.gz -O /tmp/tomcat.tar.gz
RUN cd /tmp && tar xvfz tomcat.tar.gz
RUN cp -Rv /tmp/apache-tomcat-9.0.45/* /usr/local/tomcat/
#creat folder for build and download app
RUN mkdir /boxfuse
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git /boxfuse
#building war file an cp to tomcat
RUN mvn package -f /boxfuse/pom.xml
RUN cp /boxfuse/target/hello-1.0.war /usr/local/tomcat/webapps/
# run cmd tomcat
#CMD service tomcat9 start
CMD ["/usr/local/tomcat/bin/catalina.sh","run"]
