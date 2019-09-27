FROM node:10.16-alpine

WORKDIR /action

ADD package.json package-lock.json ./
RUN npm ci --only=production

COPY ./static/locales static/locales

ENTRYPOINT ["/action/node_modules/.bin/cfy-phraseapp", "sort", "--fix"]
