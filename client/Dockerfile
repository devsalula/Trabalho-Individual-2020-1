FROM node:lts-alpine

WORKDIR /app
COPY package.json /app/package.json
RUN yarn install
COPY . .
EXPOSE 8080
RUN yarn build

CMD ["yarn", "serve"]