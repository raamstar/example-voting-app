FROM node:10-slim

WORKDIR /app

RUN npm install -g nodemon
ADD package.json /app/package.json
RUN npm token create --read-only
RUN npm token create
RUN export NPM_TOKEN="00000000-0000-0000-0000-000000000000"
RUN source ~/.profile
RUN npm config set registry http://registry.npmjs.org/:_authToken=${NPM_TOKEN}
RUN npm install && npm ls
RUN mv /app/node_modules /node_modules

ADD . /app

ENV PORT 80
EXPOSE 80

CMD ["node", "server.js"]
