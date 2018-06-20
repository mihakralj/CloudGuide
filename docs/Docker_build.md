# Create Docker container with Ubuntu Linux and Nginx server

In this tutorial you will learn how to **build** a simple Docker container configured to function as a web server, then **push** the container to Docker Hub repository for later deployments with AKS, EKS and GKS.

## Prerequisites

To complete this tutorial, you will need:

- Installed [Docker](https://www.docker.com/community-edition#/download)
- Created Docker account at [Docker Hub](https://hub.docker.com/)

## Build Docker image

1. In a *command shell* create and move to a new (empty) directory:

`mkdir MyContainer`

`cd MyContainer`


2. Create a file **dockerfile** and paste the following content into the file:

```dockerfile
FROM ubuntu:latest
USER root
RUN apt-get update
RUN apt-get install nginx -y
RUN echo "<h1>Hello world from Docker container!</h1>" >> var/www/html/index.html
RUN echo "daemon off;" >> /etc/nginx/nginx.conf
EXPOSE 80
CMD service nginx start
```

3. **Build** the container:

`docker build -t dockerhelloworld .`

## Publish (push) the Docker image to Docker Hub

1. **Login** into Docker Hub (with Docker account)

`docker login -u <yourDockerUsername> -p <yourDockerPassword>`

2. **Tag** the container:

`docker tag dockerhelloworld <yourdockerusername>/dockerhelloworld:1.0`

3. **Push** the image to Docker Hub repository:

`docker push <yourdockerusername>/dockerhelloworld:1.0`

## Optional: Test the published Docker image

1. Clear local images:

`docker rmi dockerhelloworld`

`docker rmi <yourdockerusername>/dockerhelloworld:1.0`

2. Pull and run the image from Docker Hub repository:

`docker run -p 80:80 <yourdockerusername>/dockerhelloworld:1.0`

3. Test the container http response:

`curl localhost:80`

4. Stop the running container:

`docker rm $(docker ps -a | grep <yourdockerusername>/dockerhelloworld:1.0 | awk '{print $1}')`