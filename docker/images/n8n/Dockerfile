...
RUN set -e \
 && npm install -g --omit=dev n8n@$N8N_VERSION --ignore-scripts && \
 npm rebuild && \
 rm -rf /usr/local/lib/node_modules/npm /usr/local/lib/node_modules/types && \
 rm -rf /usr/local/lib/node_modules/n8n/node_modules && \
 rm -rf /usr/local/lib/node_modules/n8n/node_modules/.bin && \
 rm -rf /usr/local/lib/node_modules/n8n/node_modules/@types && \
 rm -rf /usr/local/lib/node_modules/n8n/node_modules/@types && \
 find /usr/local/lib/node_modules/n8n -type f \( -name "*.map" -o -name "*.vue" \) | xargs rm -f

EXPOSE 5678

CMD ["n8n"]
