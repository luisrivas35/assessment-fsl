FROM node:15.14.0-alpine AS builder

WORKDIR /app

COPY package*.json package-lock.json ./

RUN npm install --engine-strict=false --legacy-per-deps

COPY . .

RUN nmp run build

FROM node:15.14.0-alpine

WORKDIR /app

RUN npm install -g serve

EXPOSE 8080

ENTRYPOINT ["serve", "-s", "build", "-l", "8080"]