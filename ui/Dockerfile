FROM node:18-alpine
COPY ./obs-web ./
RUN apk add --no-cache git && npm ci && npm run build && apk del git
EXPOSE 5000
ENTRYPOINT [ "npm", "run", "start" ]