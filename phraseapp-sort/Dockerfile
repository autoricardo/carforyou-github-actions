FROM node:10.16-alpine

ADD package.json package-lock.json ./
RUN npm ci --only=production

ADD src/static/locales ./static/locales

ENTRYPOINT ["cfy-phraseapp", "sort"]
