FROM timbru31/node-alpine-git:latest
WORKDIR /app
COPY package*.json ./
RUN npm install --production

COPY . ./

CMD npm run start
EXPOSE 3000
