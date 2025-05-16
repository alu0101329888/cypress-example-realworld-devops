FROM node:10.20.0-alpine

WORKDIR /app

RUN apk add --no-cache python3 make g++ libtool autoconf automake git

COPY package*.json ./
RUN set -e && \\
                npm config set unsafe-perm true && \\
                npm config set sodium_prebuilt_binary false && \\
                npm config set build_from_source true && \\
                mkdir -p /tmp/sodium && \\
                cd /tmp/sodium && \\
                npm pack sodium-native@3.2.0 && \\
                tar -xzf sodium-native-3.2.0.tgz && \\
                cd package && \\
                # Ejecutar autoreconf para actualizar herramientas de autoconf
                autoreconf -ivf || true && \\
                npm install --build-from-source && \\
                cd /app && \\
                # Ahora instalar todas las dependencias del proyecto
                npm install

COPY . .

EXPOSE 3000

CMD ["npm", "start"]
