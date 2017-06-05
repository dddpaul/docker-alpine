FROM smebberson/alpine-base:3.0.0
MAINTAINER Pavel Derendyaev <dddpaul@gmail.com>

# Install nginx & ssh
RUN echo "http://dl-4.alpinelinux.org/alpine/v3.3/main" >> /etc/apk/repositories && \
    apk add --update nginx=1.8.1-r1 bash git openssh && \
    rm -rf /var/cache/apk/* && \
    chown -R nginx:www-data /var/lib/nginx

# Add the files
ADD root /

# Expose the ports for nginx and ssh
EXPOSE 22 80 443
