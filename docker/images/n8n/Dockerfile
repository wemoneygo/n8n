FROM n8nio/base:20

ARG N8N_VERSION

RUN if [ -z "$N8N_VERSION" ]; then echo "The N8N_VERSION argument is missing"; exit 1; fi

LABEL org.opencontainers.image.title="n8n"
LABEL org.opencontainers.image.description="Workflow Automation Tool"
LABEL org.opencontainers.image.url="https://n8n.io/"
LABEL org.opencontainers.image.source="https://github.com/n8n-io/n8n"
LABEL org.opencontainers.image.version="${N8N_VERSION}"

ENV N8N_VERSION=${N8N_VERSION}
ENV NODE_ENV=production

RUN set -ex \
    && npm install -g --omit=dev n8n@${N8N_VERSION} --ignore-scripts && \
    npm rebuild && \
    rm -rf /usr/local/lib/node_modules/n8n/node_modules/.bin && \
    rm -rf /usr/local/lib/node_modules/n8n/node_modules/@types && \
    rm -rf /usr/local/lib/node_modules/n8n/node_modules/n8n-cli && \
    find /usr/local/lib/node_modules/n8n -type f -name "*.ts" -o -name "*.map" -o -name "*.vue" | xargs rm -f

CMD ["n8n"]
