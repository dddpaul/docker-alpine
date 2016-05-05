FROM alpine:3.3
MAINTAINER Scott Mebberson <scott@scottmebberson.com>

# Add commonly used packages
RUN apk add --no-cache bind-tools

ENV S6_OVERLAY_VERSION=v1.17.2.0 \
    GODNSMASQ_VERSION=1.0.5 \
    DOCKERIZE_VERSION=0.2.0

# Add s6-overlay, godnsmasq, dockerize
RUN apk add --no-cache curl \
    && curl -sSL https://github.com/just-containers/s6-overlay/releases/download/${S6_OVERLAY_VERSION}/s6-overlay-amd64.tar.gz | tar zxf - -C / \
    && curl -sSL https://github.com/janeczku/go-dnsmasq/releases/download/${GODNSMASQ_VERSION}/go-dnsmasq-min_linux-amd64 -o /bin/go-dnsmasq \
    && chmod +x /bin/go-dnsmasq \
    && curl -sSL https://github.com/jwilder/dockerize/releases/download/v${DOCKERIZE_VERSION}/dockerize-linux-amd64-v0.2.0.tar.gz | tar zxf - -C /bin \
    && apk del curl

ADD root /

ENTRYPOINT ["/init"]
CMD []
