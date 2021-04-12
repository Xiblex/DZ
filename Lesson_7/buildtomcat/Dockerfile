FROM openjdk:8-jre-alpine
    #Install tomcat
#WORKDIR /usr/local/tomcat


RUN wget https://mirrors.estointernet.in/apache/tomcat/tomcat-9/v9.0.44/bin/apache-tomcat-9.0.44.tar.gz -O /tmp/tomcat.tar.gz
WORKDIR /tmp
RUN tar xvfz tomcat.tar.gz \
    && cp -Rv /tmp/apache-tomcat-9.0.44/* /usr/local/tomcat/

CMD ["/usr/local/tomcat/bin/catalina.sh","run"]
