FROM dockerfile/ubuntu

MAINTAINER vlyashov@Unimelb.edu.au

# Install Nginx.
RUN apt-get install -y software-properties-common
RUN add-apt-repository -y ppa:nginx/stable
RUN apt-get update
RUN apt-get install -y nginx

# Add conf files
ADD nginx.conf /etc/nginx/nginx.conf
ADD unimelb.crt /etc/ssl/certs/unimelb.crt
ADD unimelb.key /etc/ssl/private/unimelb.key

# Attach volumes.
VOLUME /etc/nginx/sites-enabled
VOLUME /var/log/nginx

# Set working directory.
WORKDIR /etc/nginx

# Expose ports.
EXPOSE 80
EXPOSE 443

# Define default command.
ENTRYPOINT ["nginx"]

