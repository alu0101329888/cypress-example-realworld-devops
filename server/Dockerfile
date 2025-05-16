FROM node:alpine

WORKDIR /app

RUN apk add --no-cache python3 make g++ libtool autoconf build-essential automake libtool pkg-config

COPY package*.json ./

RUN npm ci
RUN npm run build

COPY . .

EXPOSE 3000

CMD ["npm", "start"]
