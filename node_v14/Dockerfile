FROM alpine:latest

ENV NODE=v14.17.2 NPM=6.14.13

RUN apk update && \
    apk upgrade
    
RUN curl -sfSLO https://nodejs.org/dist/${VERSION}/node-${VERSION}.tar.xz && \
    curl -sfSL https://nodejs.org/dist/${VERSION}/SHASUMS256.txt.asc | gpg -d -o SHASUMS256.txt && \
    grep " node-${VERSION}.tar.xz\$" SHASUMS256.txt | sha256sum -c | grep ': OK$' && \
    tar -xf node-${VERSION}.tar.xz && \
    cd node-${VERSION} && \
    ./configure --prefix=/usr ${CONFIG_FLAGS} && \
    make -j$(getconf _NPROCESSORS_ONLN) && \
    make install

RUN npm install -g npm@${NPM}; \
    node -v
    npm -v 

