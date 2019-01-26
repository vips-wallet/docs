FROM node:latest

WORKDIR /projects
RUN npm install -g aglio --unsafe-perm
CMD aglio -i md/ja.md -s -h 0.0.0.0
