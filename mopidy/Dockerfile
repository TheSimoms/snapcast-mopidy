FROM alpine:latest

ENV PYTHONUNBUFFERED=1

RUN apk add --update --no-cache python3 py3-pip mopidy

RUN python3 -m pip install \
    Mopidy-MPD \
    Mopidy-Local \
    Mopidy-Muse \
    Mopidy-Iris \
    Mopidy-Party

RUN echo "0 * * * * mopidy local scan > /root/local-scan.log" > /var/spool/cron/crontabs/root

VOLUME [ "/root" ]
VOLUME [ "/music" ]
VOLUME [ "/playlists" ]

EXPOSE 6600
EXPOSE 6680

ENTRYPOINT [ "mopidy", "--config", "/root/.config/mopidy/mopidy.conf" ]
