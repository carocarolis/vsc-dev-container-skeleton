FROM node:24-alpine

WORKDIR /app

RUN apk add --no-cache \
  python3 make g++ libc6-compat

COPY package*.json ./
RUN npm install

COPY . .

ENV CHOKIDAR_USEPOLLING=true
EXPOSE 5173

