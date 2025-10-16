FROM ghcr.io/erebe/wstunnel:latest

ENV XQUARE_SERVER_URL="" \
    PASSWORD="" \
    SERVICE_NAME="localhost" \
    SERVICE_PORT=5432

ENTRYPOINT ["/bin/sh", "-c"]
CMD ["wstunnel client \
  -L tcp://0.0.0.0:${SERVICE_PORT}:${SERVICE_NAME}:${SERVICE_PORT} \
  --http-upgrade-path-prefix \"${PASSWORD}\" \
  --connection-min-idle 5 \
  --log-lvl OFF \
  ${XQUARE_SERVER_URL}"]

EXPOSE 5432
