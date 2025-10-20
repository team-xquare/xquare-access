FROM ghcr.io/erebe/wstunnel:latest

ENV PROJECT_NAME="" \
    PASSWORD="" \
    SERVICE_NAME="localhost" \
    SERVICE_PORT=""

USER app
WORKDIR /home/app

ENTRYPOINT ["/usr/bin/dumb-init", "-v", "--"]
CMD ["/bin/sh", "-c", "exec /home/app/wstunnel client -L tcp://0.0.0.0:${SERVICE_PORT}:${SERVICE_NAME}:${SERVICE_PORT} --http-upgrade-path-prefix \"${PASSWORD}\" --log-lvl OFF ws://xquare-remote-access-${PROJECT_NAME}.dsmhs.kr"]

