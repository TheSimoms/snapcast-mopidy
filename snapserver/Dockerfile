FROM alpine:latest

RUN apk --update --no-cache add snapcast-server

RUN mkdir -p /home/snapserver && \
    addgroup -S snapserver && \
    adduser -S snapserver -G snapserver --disabled-password -h /home/snapserver && \
    chown snapserver:snapserver -R /home/snapserver

WORKDIR /home/snapserver

USER snapserver

EXPOSE 1704
EXPOSE 1705
EXPOSE 1780

VOLUME [ "/home/snapserver" ]
VOLUME [ "/tmp" ]

ENTRYPOINT [ "snapserver", "--config", "/home/snapserver/snapserver.conf" ]
