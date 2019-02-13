FROM node:10.15.1-alpine

RUN apk --no-cache add make g++ python inotify-tools
RUN npm i -g --unsafe-perm snowboard@1.8.12
RUN apk del make g++ python
RUN mkdir /doc

WORKDIR /doc
VOLUME /doc
EXPOSE 8087 8088
ENTRYPOINT ["snowboard"]
