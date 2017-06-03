FROM anapsix/alpine-java:8
MAINTAINER Pavel Derendyaev <dddpaul@gmail.com>
RUN apk add --update bash \
  python python-dev py-pip \
  && rm -rf /var/cache/apk/*
ADD play-1.3.tar.gz /
EXPOSE 9000
