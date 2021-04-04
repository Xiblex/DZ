FROM ubuntu:20.04
#Timezone
ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
EXPOSE 8080
#install packages
RUN apt-get update
RUN apt-get install tomcat9 maven git -y
#stop and disable tomcat9
RUN systemctl stop tomcat9
RUN systemctl disable tomcat9
#creat folder for build and download app
RUN mkdir /boxfuse
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git /boxfuse
#building war file an cp to tomcat
RUN mvn package -f /boxfuse/pom.xml
RUN cp /boxfuse/target/hello-1.0.war /var/lib/tomcat9/webapps/
# run cm tomcat from oficial dockerfile
CMD ["/usr/share/tomcat9/bin/catalina.sh" "run"]
