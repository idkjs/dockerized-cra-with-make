# How to dockerize your ReactJS app for development in a container

[source](https://medium.com/@thexap/how-to-dockerize-your-reactjs-app-ad618a48ad6b)

Create your Docker image to run a React JS app

## Table of contents

1.  Create Dockerfile

1.  Create docker compose file

1.  Create Makefile

1.  Start the app

## 1) Create Dockerfile

Lets use a node 8 base image and create an app folder that will hold our source code.

We are going to be able to modify the source code files in our computer and it will automatically reflect the changes to the docker image, using the live reload functionality.

<iframe src="https://medium.com/media/b631a820a9497b35ed17824b36a98e61" frameborder=0></iframe>

## 2) Create docker compose file

Lest create the docker-compose.yml file.

We are using the Dockerfile that we created earlier, we are using the volume tag to reflect the files from the computer to the docker image. We are taking the current folder and using to map it with the folder created in the docker image.

Finally, we use the entrypoint so that the container doesn’t exit.

<iframe src="https://medium.com/media/3d9b75b15105986a3c77327d0d1d6cf9" frameborder=0></iframe>

## 3) Create the Makefile

Lest create a Makefile that is going to hold the commands to start, stop the image. Also, it is going to have the commands to install and start the app

<iframe src="https://medium.com/media/b77fdcbe99067ca270fb35afe5fa945b" frameborder=0></iframe>

## 4) Start the app

Start the docker image with

    make start-docker-image

Start the app with

    make watch

Open the browser and run the app. For example: localhost:3000

Open `src/App.js` and change something to see your browser hot reload.

Thanks to [mediumexport](https://github.com/xdamman/mediumexporter)
