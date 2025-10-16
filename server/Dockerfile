FROM ghcr.io/erebe/wstunnel:latest

ENV PORT=8080 \
    PASSWORD="" \
    LOG_LEVEL=INFO

HEALTHCHECK --interval=30s --timeout=10s --start-period=5s --retries=3 \
  CMD timeout 5 sh -c 'echo -e "GET / HTTP/1.1\r\nHost: localhost\r\n\r\n" | nc localhost ${PORT}' || exit 1

USER app
WORKDIR /home/app

ENTRYPOINT ["/usr/bin/dumb-init", "-v", "--"]
CMD ["/bin/sh", "-c", "exec /home/app/wstunnel server --restrict-http-upgrade-path-prefix \"${PASSWORD}\" --log-lvl ${LOG_LEVEL} ws://0.0.0.0:${PORT}"]

EXPOSE 8080
