FROM alpine:latest

ENV NODE=v14.17.2 NPM=6.14.13

RUN apk update && \
    apk upgrade
    
RUN curl -sfSLO https://nodejs.org/dist/v14.17.2/node-v14.17.2.tar.xz && \
    curl -sfSL https://nodejs.org/dist/v14.17.2/SHASUMS256.txt.asc | gpg -d -o SHASUMS256.txt && \
    grep " node-v14.17.2.tar.xz\$" SHASUMS256.txt | sha256sum -c | grep ': OK$' && \
    tar -xf node-v14.17.2.tar.xz && \
    cd node-v14.17.2 && \
    make install

RUN npm install -g npm@6.14.13 \
    node -v \
    npm -v 

