FROM node:10.20.0-alpine

WORKDIR /app

RUN apk add --no-cache python3 make g++ libtool autoconf automake libtool pkgconf

COPY package*.json ./

RUN npm ci
RUN npm run build

COPY . .

EXPOSE 3000

CMD ["npm", "start"]
