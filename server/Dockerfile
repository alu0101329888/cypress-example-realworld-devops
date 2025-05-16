FROM node:10.20.0-alpine

WORKDIR /app

RUN apk add --no-cache python3 make g++ libtool autoconf automake git

COPY package*.json ./
RUN set -e
RUN npm config set unsafe-perm true
RUN npm config set sodium_prebuilt_binary false
RUN npm config set build_from_source true
RUN mkdir -p /tmp/sodium
RUN cd /tmp/sodium
RUN npm pack sodium-native@3.2.0
RUN tar -xzf sodium-native-3.2.0.tgz
RUN cd package
RUN autoreconf -ivf || true
RUN npm install --build-from-source
RUN cd /app
NPM npm install

COPY . .

EXPOSE 3000

CMD ["npm", "start"]
