# Docker Guide

Docker Consistently build, run and ship applications

## Container

An Isolated environment for running an application
- Allow running multiple apps in isolation
- Are lightweight
- Use OS of the host
- Start quickly
- Need less hardware resources

# Virtual Machine
An abstraction of a machine (physical hardware)

# Docker
Clint > Rest API > Docker Engine

# Installing Docker
https://docs.docker.com/desktop/setup/install/windows-install/

https://app.docker.com

# Docker Hub
https://hub.docker.com


# Create app.js
        Input 
        console.log("Hello Docker!");

# Create Dockerfile

        FROM node:alpine
        COPY . /app
        WORKDIR /app
        CMD node app.js

# Build image 
docker build -t hello-docker

# Check image
docker images
docker image ls

# Run Docker image 
docker run hello-docker



# Docker-AWS

# Create folder for HTML
- Create folder src > html
- Create index.html 
- Input the html code
        
        !DOCTYPE html>
        <html>

        <body>
            <h1>My First Web Page</h1>
            <h1>It works on my machine...</h1>
            <h1>and works on every machine!</h1>
            <p>My Web Page is running on Docker</p>
            <img src="docker.png" alt="Docker Logo" width="450" height="350">
        </body>

        </html>

# Create a Dockerfile
# Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image.

        FROM nginx:1.27.4-alpine-slim
        COPY src/html /usr/share/nginx/html

# Build the image
    - docker build -t hello-wolrd .

# Check image
    - docker images

# Run docker
    - docker run -d -p 80:80 ca79e6e90073(image ID)
    - -p to pass the port 
# Check if website running
    type localhost in website

# Check running docker
    - docker ps
# Stop running docker 
    - docker stop (image name) 

# docker did not delete the docker it just stop
    - Check all docker -= docker ps -all

# start docker again
    - docker start (image name)

# remove docker container
    docker rm (image name)

# remove docker image 
    docker rmi (image ID)

# Ignore file to be put in image 
    Create a file .dockerignore
        put the file name you want to be ignore/