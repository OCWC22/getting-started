# syntax=docker/dockerfile:!
#This command used the Dockerfile to build a new container image. 
#You might have noticed that a lot of “layers” were downloaded. 
#This is because we instructed the builder that we wanted to start from the node:12-alpine image. 
#But, since we didn’t have that on our machine, that image needed to be downloaded.
FROM node:12-alpine
RUN apk add --no-cache python2 g++ make 
WORKDIR /app
COPY . .
#After the image was downloaded, we copied in our application and used yarn to install our 
#application’s dependencies. 
RUN yarn install --production 
#The CMD directive specifies the default command to run when starting a 
#container from this image.
CMD ["node", "src/index.js"]
EXPOSE 3000




#This command used the Dockerfile to build a new container image.
# docker build -t getting-started .

#Finally, the -t flag tags our image. Think of this simply as a human-readable name for the final image. Since we named the image getting-started, we can refer to that image when we run a container.

#The . at the end of the docker build command tells Docker that it should look for the Dockerfile in the current directory.