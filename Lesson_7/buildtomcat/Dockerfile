FROM openjdk:8-jre-alpine
    #Install tomcat
#WORKDIR /usr/local/tomcat


RUN wget https://mirrors.nav.ro/apache/tomcat/tomcat-8/v8.5.65/bin/apache-tomcat-8.5.65.tar.gz -O /tmp/apache-tomcat-8.5.65.tar.gz
WORKDIR /tmp
RUN tar xvfz tomcat.tar.gz \
    && cp -Rv /tmp/apache-tomcat-9.0.44/* /usr/local/tomcat/

CMD ["/usr/local/tomcat/bin/catalina.sh","run"]
