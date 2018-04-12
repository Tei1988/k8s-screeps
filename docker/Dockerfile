FROM node:8-alpine
MAINTAINER Tei1988 <tei1988@grifola.xyz>

ENV VERSION 2.13.1

RUN apk --update --no-cache add --virtual .build-deps python make g++ && \
    yarn global add screeps@${VERSION} && \
    mkdir -p /screeps && \
    chown -R node. /screeps && \
    apk del --purge .build-deps

USER node
COPY entrypoint.sh /usr/local/bin/
WORKDIR /screeps

ENTRYPOINT ["entrypoint.sh"]
CMD ["screeps", "start"]
