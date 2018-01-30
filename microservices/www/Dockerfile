FROM node:6-slim

WORKDIR /starter

COPY src/package.json /starter/package.json
COPY src/.env.example /starter/.env.example

ENV NODE_ENV production
RUN npm install --production

COPY src /starter

CMD ["npm","start"]
