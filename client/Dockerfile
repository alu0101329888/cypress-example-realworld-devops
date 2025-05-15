FROM node:18-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

# Asegurarse de que la aplicación escuche en todos los interfaces
ENV HOST=0.0.0.0
ENV PORT=4100

EXPOSE 4100

CMD ["npm", "start"]
