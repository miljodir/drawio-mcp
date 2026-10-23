FROM node:lts-alpine

WORKDIR /app

COPY --link mcp-tool-server/package*.json ./
RUN npm ci --omit=dev --ignore-scripts

COPY --link mcp-tool-server/src ./src
COPY --link mcp-tool-server/vendor ./vendor
COPY --link shared/xml-reference.md shared/mermaid-reference.md shared/shape-search.js shared/icon-search.js ./src/
COPY --link shape-search/search-index.json ./src/search-index.json

USER node

CMD ["node", "src/index.js"]