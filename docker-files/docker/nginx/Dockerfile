FROM nginx:latest

LABEL maintainer="Stuart McCord"

#WORKDIR /var/www/html

COPY h5bp /etc/nginx/h5bp
COPY default /etc/nginx/conf.d/default.conf

EXPOSE 80

ENTRYPOINT ["nginx", "-g", "daemon off;"]