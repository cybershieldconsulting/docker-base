FROM alpine:3.3

ENV LANG en_US.UTF-8
ENV MITM_VER git+https://github.com/mitmproxy/mitmproxy.git@master

RUN apk add --no-cache \
        git \
        g++ \
        py-pip \
        libffi \
        libffi-dev \
        libjpeg-turbo \
        libjpeg-turbo-dev \
        libxml2 \
        libxml2-dev \
        libxslt \
        libxslt-dev \
        openssl \
        openssl-dev \
        python \
        python-dev \
        zlib \
        zlib-dev \
 && adduser -u 7799 -D mitmproxy

ONBUILD RUN LDFLAGS=-L/lib pip install $MITM_VER \
    && apk del --purge \
        git \
        g++ \
        libffi-dev \
        libjpeg-turbo-dev \
        libxml2-dev \
        libxslt-dev \
        openssl-dev \
        python-dev \
        zlib-dev \
    && rm -rf ~/.cache/pip
ONBUILD USER mitmproxy
ONBUILD RUN mkdir /home/mitmproxy/.mitmproxy
ONBUILD VOLUME /home/mitmproxy/.mitmproxy

EXPOSE 8080 8081
CMD ["mitmproxy"]
