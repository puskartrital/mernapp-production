FROM node:alpine as builder
LABEL maintainer="pt@puskartrital.com"
LABEL version="1.0"

LABEL description="React Frontend for the Server API"

WORKDIR /app

COPY ./package.json ./

RUN npm install -g npm-check-updates && ncu -u && npm install

COPY . .

RUN npm run build 

FROM nginx

EXPOSE 3000

COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf

COPY --from=builder /app/build /usr/share/nginx/html

