FROM node:alpine

WORKDIR /app

RUN apk add --no-cache python3 make g++

COPY package*.json ./

RUN npm install --unsafe-perm=true

COPY . .

# Asegurarse de que la aplicación escuche en todos los interfaces
ENV HOST=0.0.0.0
ENV PORT=4100

EXPOSE 4100

CMD ["npm", "start"]
