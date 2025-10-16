FROM ghcr.io/erebe/wstunnel:latest

ENV PROJECT_NAME="" \
    PASSWORD="" \
    SERVICE_NAME="localhost" \
    SERVICE_PORT=5432

CMD ["/bin/sh", "-c", "wstunnel client -L tcp://0.0.0.0:${SERVICE_PORT}:${SERVICE_NAME}:${SERVICE_PORT} --http-upgrade-path-prefix \"${PASSWORD}\" --connection-min-idle 5 --log-lvl OFF ws://xquare-remote-access-${PROJECT_NAME}.dsmhs.kr"]

EXPOSE 5432
