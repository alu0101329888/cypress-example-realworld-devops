FROM node:18-alpine

WORKDIR /app

RUN apk add --no-cache python3 make g++ libtool autoconf automake

COPY package*.json ./
RUN npm install --unsafe-perm=true

COPY . .

EXPOSE 3000

CMD ["npm", "start"]
