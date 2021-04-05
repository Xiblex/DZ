FROM ubuntu:16.04
EXPOSE 5000
ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y -q python-all python-pip
ADD requirements.txt /tmp/
WORKDIR /tmp/
RUN pip install -qr requirements.txt
WORKDIR /opt/webapp
ADD app.py
CMD python app.py