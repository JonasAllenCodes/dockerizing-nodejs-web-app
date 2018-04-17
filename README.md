# DOCKERIZING A NODE.JS WEB APP

This is just a follow along with ["Dockerizing a Node.js Web App"](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/) on the [Node.JS website](https://nodejs.org/). 

## Instructions

Follow instructions bellow to get up and running

### Run the Image

Run:

 $ `docker run -p 49160:8080 -d jonasallencodes/dockerizing-nodejs-web-app`

If you want to run the container in detached mode (run in the background), make sure to include the -d tag. You will need the -p tag, this tag routes the exposed container port to the host machines port. So "49160" is the port that is forwarding to the container's exposed port "8080". You must keep the port "8080" as it is the port exposed in the "Dockerfile". If you want to change the container's exposed port you will need to also change in the "Dockerfile" after "EXPOSE". Now you may need to change the port being used on the host machine if it is already being used or for other reasons. To do so you only need to change "49160" in the above command.

### Getting Docker Image Info

You can get information on the running docker image by running:

$ `docker ps`

From here on out I will refer to Container ID or Name as `<container id>`.

### Go into Container Terminal

If you need to go into the container terminal you can run the following:

$ `docker logs <container id>`

### Test App

To test the app in the Terminal run:

$ `curl -i localhost:49160`

You should see app status and info along with app output.

To test the app out in the browser go to [http://localhost:49160](http://localhost:49160) in your browser.

### End Container Process

Now to shutdown the container process you will need to run:

`docker container stop <container id>`