FROM node:alpine

WORKDIR /app

RUN apk add --no-cache python3 make g++ libtool autoconf build-essential automake libtool pkg-config

COPY package*.json ./

RUN npm install --unsafe-pref=true

COPY . .

EXPOSE 3000

CMD ["npm", "start"]
