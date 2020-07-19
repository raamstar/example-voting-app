FROM node:10-slim

WORKDIR /app

RUN npm install -g nodemon
ADD package.json /app/package.json
RUN npm config set registry http://registry.npmjs.org/:_authToken=GFYR$E8D-89DG-GH54-HJDR-TYDGOSYT785T  
RUN npm install && npm ls
RUN mv /app/node_modules /node_modules

ADD . /app

ENV PORT 80
EXPOSE 80

CMD ["node", "server.js"]
