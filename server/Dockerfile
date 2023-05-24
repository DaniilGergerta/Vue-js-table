FROM node:14-alpine

WORKDIR /usr/src/app/server

RUN chown -R node:node /usr/src/app/server

USER node

COPY --chown=node:node package*.json ./

RUN npm install
COPY --chown=node:node . ./

EXPOSE 3000

CMD [ "npm", "start" ]