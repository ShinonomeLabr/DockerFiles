FROM ubuntu:14.04

ARG NODE_ENV="docker"
ARG NODE_VERSION="6.9.1"
ARG NODE_PATH="/usr/lib/node_modules:/usr/local/lib/node_modules"
ARG INS_VIM="true"
ARG INS_GIT="true"

RUN mkdir -p /usr/src/clustercc 
WORKDIR /usr/src/clustercc 

RUN apt-get -qq update
RUN apt-get -yqq install npm
RUN apt-get -yqq install curl
RUN npm config set registry="http://registry.npmjs.org"
RUN npm install -g n
RUN n "$NODE_VERSION"

RUN if [ ${INS_VIM} = "true" ]; then \
    apt-get -yqq install vim \
;fi
RUN if [ ${INS_GIT} = "true" ]; then \
    apt-get -yqq install git \
;fi

RUN apt-get install -yqq libcairo2-dev libjpeg8-dev libpango1.0-dev libgif-dev build-essential g++
RUN npm install -g canvas
RUN ln -s /usr/local/lib/node_modules /usr/local
RUN npm install -g mocha

ENV NODE_PATH=$NODE_PATH
ENV NODE_ENV=$NODE_ENV

EXPOSE 3000
CMD ["node", "server/server.js"]
