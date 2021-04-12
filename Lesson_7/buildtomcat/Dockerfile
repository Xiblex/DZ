FROM openjdk:8-jre-alpine
RUN apt-get update \
    && apt-get install -y --no-install-recommends wget \
    && rm -rf /var/lib/apt/lists/*
    #Install tomcat
RUN mkdir /usr/local/tomcat \
    && wget https://mirrors.estointernet.in/apache/tomcat/tomcat-9/v9.0.44/bin/apache-tomcat-9.0.44.tar.gz -O /tmp/tomcat.tar.gz \
    && cd /tmp && tar xvfz tomcat.tar.gz \
    && cp -Rv /tmp/apache-tomcat-9.0.44/* /usr/local/tomcat/
CMD ["/usr/local/tomcat/bin/catalina.sh","run"]
