FROM ubuntu:18.04
RUN apt update -y
RUN apt upgrade -y
#RUN apt-get install -y python-software-properties
RUN apt-get install -y software-properties-common
RUN add-apt-repository -y ppa:nginx/stable
RUN apt-get update -y
RUN apt-get install -y nginx
# deamon mode off
RUN echo "\ndaemon off;" >> /etc/nginx/nginx.conf
RUN chown -R www-data:www-data /var/lib/nginx
COPY ./app /app
# expose ports
EXPOSE 80 443
# add nginx conf
#ADD config/nginx.conf /etc/nginx/conf.d/default.conf
WORKDIR /etc/nginx
CMD ["nginx"]
