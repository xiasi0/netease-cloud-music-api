ARG BUILD_FROM
FROM ${BUILD_FROM}

SHELL ["/bin/ash", "-o", "pipefail", "-c"]

RUN apk add --no-cache nodejs npm git

WORKDIR /opt/netease-api

RUN git clone --depth=1 https://github.com/NeteaseCloudMusicApiEnhanced/api-enhanced.git . \
    && npm install --omit=dev --no-fund --no-audit \
    && npm cache clean --force

COPY rootfs /

RUN chmod +x /run.sh

EXPOSE 3000

CMD ["/run.sh"]
