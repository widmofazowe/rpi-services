FROM node:14.15.0-alpine
RUN apk update && apk add git
WORKDIR /app
COPY package*.json ./
RUN npm install --production

COPY . ./

CMD npm run start
EXPOSE 3000
