FROM node:6-slim

COPY src /starter
COPY src/package.json /starter/package.json
COPY src/.env.example /starter/.env.example

WORKDIR /starter

ENV NODE_ENV production
RUN npm install --production

CMD ["npm","start"]
