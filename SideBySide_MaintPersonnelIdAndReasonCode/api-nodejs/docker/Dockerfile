FROM --platform=linux/amd64 node:current-slim

# Install node/npm
RUN apt-get update && apt-get install -y curl
RUN apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash - 
RUN apt-get install -y nodejs 
RUN apt-get install -y dos2unix 
#RUN npm

# Create app directory
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

# Install app dependencies
COPY app/package.json /usr/src/app/
RUN npm install

# Bundle app source
COPY app /usr/src/app

EXPOSE 8080

CMD npm start