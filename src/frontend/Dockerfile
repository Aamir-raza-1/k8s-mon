# Dependencies stage
FROM node:lts-alpine as builder
COPY package*.json ./
RUN npm install

# Application stage
FROM node:lts-alpine
WORKDIR /usr/src/app
COPY --from=builder node_modules node_modules
COPY . .
EXPOSE 8080
CMD [ "node", "app.js" ]