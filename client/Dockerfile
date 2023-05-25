FROM node:alpine

RUN apk add --no-cache libc6-compat
RUN npm i -g npm

WORKDIR /usr/src/app/client
RUN chown -R node:node /usr/src/app/client

COPY --chown=node:node package.json .

RUN npm install --omit=optional --force
RUN npx browserslist@latest --update-db

COPY --chown=node:node . .

USER node

EXPOSE 5173

ENTRYPOINT ["npm", "run", "dev"]