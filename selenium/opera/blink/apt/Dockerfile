FROM selenoid/base:1.0

ARG VERSION
ARG CLEANUP

RUN  \
        ( [ "$CLEANUP" != "true" ] && rm -f /etc/apt/apt.conf.d/docker-clean ) || true && \
        wget -O- http://deb.opera.com/archive.key | apt-key add - && \
        echo 'deb http://deb.opera.com/opera-stable/ stable non-free' > /etc/apt/sources.list.d/opera-blink.list && \
        apt-get update && \
        apt-get -y install opera-stable=$VERSION && \
        ($CLEANUP && rm -Rf /tmp/*) || true