FROM node:erbium-slim

RUN mkdir -p /var/log
COPY server/ /src/server
COPY resources/ /src/resources
COPY site/ /src/site
COPY tools/ /src/tools
COPY ui/ /src/ui
WORKDIR /src/server
RUN npm install

RUN cp /src/server/config/config_docker_template.json /src/server/config/config_docker.json
#RUN cp /src/server/config/config_cicd_template.json /src/server/config/config_cicd.json

ARG NODE_ENV=docker
ENV NODE_ENV=$NODE_ENV

EXPOSE 3000
CMD ["node", "lib/app.js"]
