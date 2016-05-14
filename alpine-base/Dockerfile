FROM alpine:3.3
MAINTAINER Scott Mebberson <scott@scottmebberson.com>

# Add commonly used packages
RUN apk add --no-cache bind-tools

ENV S6_OVERLAY_VERSION=v1.17.2.0 \
    DOCKERIZE_VERSION=0.2.0

# Add s6-overlay, godnsmasq, dockerize
RUN apk add --no-cache curl \
    && curl -sSL https://github.com/just-containers/s6-overlay/releases/download/${S6_OVERLAY_VERSION}/s6-overlay-amd64.tar.gz | tar zxf - -C / \
    && curl -sSL https://github.com/jwilder/dockerize/releases/download/v${DOCKERIZE_VERSION}/dockerize-linux-amd64-v0.2.0.tar.gz | tar zxf - -C /bin \
    && apk del curl

ADD root /

ENTRYPOINT ["/init"]
CMD []
