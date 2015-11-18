FROM python:2.7
EXPOSE 8080
EXPOSE 8081
VOLUME /certs
ENTRYPOINT /bin/bash
ONBUILD RUN mkdir -p /tmp/mitmproxy
ONBUILD COPY requirements.txt /tmp/mitmproxy
ONBUILD RUN pip install --no-cache-dir -r requirements.txt && rm -rf /tmp/mitmproxy
