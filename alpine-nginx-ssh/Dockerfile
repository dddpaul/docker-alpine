FROM smebberson/alpine-base:3.0.0
MAINTAINER Pavel Derendyaev <dddpaul@gmail.com>

# Taken from https://github.com/docker/dockercloud-authorizedkeys
ENV AUTHORIZED_KEYS **None**

# Install nginx & ssh
RUN echo "http://dl-4.alpinelinux.org/alpine/v3.3/main" >> /etc/apk/repositories && \
    apk add --update nginx=1.8.1-r1 bash git openssh && \
    rm -rf /var/cache/apk/* && \
    chown -R nginx:www-data /var/lib/nginx

# Generate host ssh keys and enable ssh for root
RUN mkdir -p /root/.ssh && \
    chmod 700 /root/.ssh && \
    echo -e "\nPermitRootLogin yes\n" >> /etc/ssh/sshd_config && \
    ssh-keygen -A && \
    cp -a /etc/ssh /etc/ssh.cache

# Add the files
ADD root /

# Expose the ports for nginx and ssh
EXPOSE 22 80 443
