#### before running the docker file a default file
####needs to be created with the following content

#server {
#    root /var/www;
#    index index.html index.htm;
#
#    # Make site accessible from http://localhost/
#    server_name localhost;
#
#    location / {
#        # First attempt to serve request as file, then
#        # as directory, then fall back to index.html
#        try_files $uri $uri/ /index.html;
#    }
#}

FROM jcandlin/ubuntu-base:0.2

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get -y install nginx

RUN echo "daemon off;" >> /etc/nginx/nginx.conf
RUN mkdir /etc/nginx/ssl
ADD default /etc/nginx/sites-available/default

EXPOSE 80

CMD ["nginx"]
