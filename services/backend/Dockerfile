FROM node:20-alpine as base

RUN mkdir /home/node/app && chown node:node /home/node/app
RUN mkdir /home/node/app/node_modules && chown node:node /home/node/app/node_modules

WORKDIR  /home/node/app

USER node

COPY --chown=node:node package.json package-lock.json ./

RUN npm ci

COPY --chown=node:node . .

ENTRYPOINT [ "npm", "run", "start"]

EXPOSE 3000