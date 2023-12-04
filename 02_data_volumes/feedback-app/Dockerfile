FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY .. .

#arguments cannot be used in CMD command
ARG DEFAULT_PORT=80

#anounce environament variable; can be referenced in code for example in node: process.env.PORT
ENV PORT $DEFAULT_PORT

EXPOSE $PORT

#anonymous volume
#path inside of the container wich should be maped to some folder outside the container; docker manages where the volume is stored on disk
# VOLUME [ "/app/feedback" ]

# VOLUME [ "/app/node_modules" ]

#CMD [ "node", "server.js" ]

#npm autoamticaly restarts when js files changes ; does not work in windows
CMD [ "npm", "start" ]
