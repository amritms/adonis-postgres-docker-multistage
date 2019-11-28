FROM node:12-alpine as base

WORKDIR /src
COPY package.json package-lock.json /src/
COPY . /src
EXPOSE 3333
RUN npm i -g @adonisjs/cli

FROM base as production
ENV NODE_ENV=production
RUN npm install --production
CMD ["node", "start"]

FROM base as dev
ENV NODE_ENV=development
RUN npm install
CMD ["npm", "run", "dev"]
