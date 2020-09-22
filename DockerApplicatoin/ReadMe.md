To create docker image
Download docker desktop from https://docs.docker.com/install
Create asp.net core application. Give commands in dockerfile
Goto Commandprompt -> navigate to the project folder where docker file exists
Run the following command to build and create docker image
docker build --tag dockerdemo:v3 .
Run the following command to create view the docker image
docker images
Run the following command to run the application using docker
docker run -it --rm -p 8080:80 dockerdemo:v3
