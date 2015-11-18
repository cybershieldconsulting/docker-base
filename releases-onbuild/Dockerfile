FROM python:2.7
EXPOSE 8080
EXPOSE 8081
VOLUME /certs
ENTRYPOINT /bin/bash
ONBUILD WORKDIR /tmp/mitmproxy
ONBUILD COPY requirements.txt /tmp/mitmproxy/
ONBUILD RUN [ ! -e requirements.txt ] || pip install --no-cache-dir -r requirements.txt
