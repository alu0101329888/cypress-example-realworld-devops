FROM node:18-alpine

WORKDIR /app

RUN apk add --no-cache python3 make g++ libtool autoconf automake

COPY package*.json ./
RUN npm config set unsafe-perm true
RUN npm install

COPY . .

EXPOSE 3000

CMD ["npm", "start"]
