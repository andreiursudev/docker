FROM node:12

#all commands will run in this folder
WORKDIR /app

#Layed based arhitecture
#when building the image docker checks if package.json from the image has any differences from the package.json from disk.
#if there are changes next steps will be ran again and not loaded from the cache
COPY package.json /app

RUN npm install

#copy ouside to insede of immage; could use COPY . . since workdir is /app
COPY . /app

#EXPOSE only documents that port 80 will be exposed outside the container
#command to expose to port: docker run -p 3000:80
#-p = publish
EXPOSE 80

#CMD will be executed when the image is created but when the container is started
#If you dont secify a CMD, the CMD of the base image  will be executed. With no base image and no CMD, you'd get an error
#CMD should be the last command in you rocker file
CMD ["node", "server.js"]