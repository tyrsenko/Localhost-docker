FROM nginx:1.12
MAINTAINER Tonya

RUN apt-get update && apt-get upgrade -y && apt-get install -y nginx wget curl vim

ADD ./LH1/ /var/www/LH1.com/public/ 
ADD ./LH2/ /var/www/LH2.com/public/
ADD ./nginxconf/ /etc/nginx/sites-available/
RUN rm -v /etc/nginx/conf.d/*
RUN rm -v /usr/share/nginx/html/*
RUN rm -v /etc/nginx/nginx.conf
ADD ./nginx/ /etc/nginx/

RUN mkdir /etc/nginx/sites-enabled/
RUN ln -s /etc/nginx/sites-available/LH1.com /etc/nginx/sites-enabled/
RUN ln -s /etc/nginx/sites-available/LH2.com /etc/nginx/sites-enabled/

RUN echo "172.17.0.2	LH1.com www.LH1.com" >> /etc/hosts
RUN echo "172.17.0.2	LH1.com www.LH1.com" >> /etc/hosts

EXPOSE 80
