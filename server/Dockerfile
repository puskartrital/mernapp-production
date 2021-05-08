FROM node:alpine

LABEL version="1.0"
LABEL description="Production image for the Server MERN API"

WORKDIR /app

COPY ["package.json","package-lock.json*","npm-shrinkwrap.json*", "./"]
RUN npm install -g npm-check-updates && ncu -u && npm install

COPY . .

CMD [ "npm", "run", "start" ]