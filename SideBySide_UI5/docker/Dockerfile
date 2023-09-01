# build environment
FROM --platform=linux/amd64  node:current-slim as build
ENV VERSION 0.1
RUN ls
WORKDIR /app
RUN ls
COPY package.json ./
RUN npm install
COPY . .
RUN npm run-script build

# production environment
FROM --platform=linux/amd64 nginx:alpine
ENV VERSION 0.1
COPY --from=build /app/dist /usr/share/nginx/html
