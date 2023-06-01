FROM node:current-alpine3.16
RUN apk add --no-cache tzdata
ENV TZ Europe/Kyiv
ENV NODE_PATH /opt/server/node_modules

WORKDIR /opt/server/

CMD [ "node" ]