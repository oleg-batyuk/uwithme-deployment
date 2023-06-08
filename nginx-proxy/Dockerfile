FROM ubuntu:20.04

ENV TZ=Europe/Kiev
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update

RUN apt-get install -y apache2

COPY ./apache.conf /etc/apache2/site-enabled/apache.conf

EXPOSE 80
EXPOSE 8443

CMD ["/usr/sbin/apache2ctl", "-D","FOREGROUND"]