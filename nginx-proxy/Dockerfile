FROM ubuntu:20.04

ENV TZ=Europe/Kiev
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update

RUN apt-get install -y apache2

COPY ./apache.conf /etc/apache2/sites-enabled/apache.conf

RUN a2enmod proxy
RUN a2enmod headers
RUN a2enmod ssl
RUN a2enmod proxy
RUN a2enmod proxy_balancer
RUN a2enmod proxy_http
RUN a2enmod proxy_wstunnel

EXPOSE 80
EXPOSE 443

CMD ["/usr/sbin/apache2ctl", "-D","FOREGROUND"]