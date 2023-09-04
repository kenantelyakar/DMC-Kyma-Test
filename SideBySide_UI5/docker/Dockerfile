# build environment
FROM --platform=linux/amd64  node:current-slim as build
ENV VERSION 0.1
#COPY . .
WORKDIR /app
COPY SideBySide_UI5/package.json .
RUN npm install
COPY . .
RUN cd /app; npm run-script build

# production environment
FROM --platform=linux/amd64 nginx:alpine
ENV VERSION 0.1
COPY --from=build /app/dist /usr/share/nginx/html
