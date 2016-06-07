FROM alpine:latest
MAINTAINER uraura <t@urau.la>

RUN set -x \
  && apk update \
  && apk add python py-pygments ctags libtool \
  && apk add --virtual build-deps \
    autoconf automake bison flex gperf g++ ncurses-dev make texinfo

ENV GLOBAL_VER 6.5.4
ADD http://tamacom.com/global/global-$GLOBAL_VER.tar.gz /tmp/
RUN set -x \
  && cd /tmp \
  && tar xzf global-$GLOBAL_VER.tar.gz \
  && cd /tmp/global-$GLOBAL_VER \
  && ./configure --with-exuberant-ctags=/usr/bin/ctags \
  && make \
  && make install \
  && apk del build-deps
RUN set -x \
  && cp /usr/local/share/gtags/gtags.conf /etc/gtags.conf \
  && rm -rf /tmp/global-$GLOBAL_VER /tmp/global-$GLOBAL_VER.tar.gz

WORKDIR /src
