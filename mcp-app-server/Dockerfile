FROM node:lts-alpine

WORKDIR /app

COPY --link package*.json ./
RUN npm ci --omit=dev

COPY --link src ./src

CMD ["node", "src/index.js"]

EXPOSE 3001 