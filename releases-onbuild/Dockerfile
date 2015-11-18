FROM python:2.7
EXPOSE 8080
EXPOSE 8081
VOLUME /certs
ENTRYPOINT /bin/bash
ONBUILD COPY requirements.txt /tmp/requirements.txt
ONBUILD RUN [ ! -e /tmp/requirements.txt ] || \
          pip install --no-cache-dir -r /tmp/requirements.txt && \
          rm -rf /tmp/requirements.txt
