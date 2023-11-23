FROM alpine:latest

RUN echo "https://dl-cdn.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories \
    && apk --update --no-cache add snapcast-server librespot

EXPOSE 1704
EXPOSE 1705
EXPOSE 1780

VOLUME [ "/etc/snapcast" ]

ENTRYPOINT [ "snapserver", "--config", "/etc/snapcast/snapserver.conf" ]
