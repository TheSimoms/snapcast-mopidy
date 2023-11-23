FROM alpine:latest

ENV PYTHONUNBUFFERED=1

RUN echo "https://dl-cdn.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories \
    && apk add --update --no-cache python3 py3-pip gst-plugins-base gst-plugins-good gst-plugins-bad gst-plugins-ugly mopidy

RUN python3 -m pip install \
    Mopidy-MPD \
    Mopidy-Local \
    Mopidy-Iris \
    Mopidy-Party

RUN echo "0 * * * * mopidy local scan" > /var/spool/cron/crontabs/root

VOLUME [ "/root" ]
VOLUME [ "/music" ]
VOLUME [ "/playlists" ]
VOLUME [ "/fifo" ]

EXPOSE 6600
EXPOSE 6680

ENTRYPOINT [ "mopidy", "--config", "/root/.config/mopidy/mopidy.conf" ]
