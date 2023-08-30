FROM alpine:latest

ENV PYTHONUNBUFFERED=1

RUN apk add --update --no-cache python3 py3-pip mopidy

RUN python3 -m pip install \
    Mopidy-MPD \
    Mopidy-Iris \
    Mopidy-Jellyfin \
    Mopidy-Party

USER mopidy

VOLUME [ "/var/lib/mopidy" ]
VOLUME [ "/tmp" ]

EXPOSE 6600
EXPOSE 6680

ENTRYPOINT [ "mopidy", "--config", "/var/lib/mopidy/mopidy.conf" ]
