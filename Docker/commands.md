
# Docker Commands 

# docker --version 
It displays the currently installed version of Docker on your system.

# docker info
Displays detailed information about your Docker environment (system-wide details).

# docker compose version 
This command shows the installed version of Docker Compose (v2) on your system.

# docker run hello-world
This command is used to test whether Docker is installed and working correctly.
* hello-world is a docker images which is pulled from docker hub 
* every docker iamges has unique image id which is automatically created by docker .
* Each Docker container is assigned a unique Container ID when it is created, which is used to identify and manage the container.

# docker ps 
It shows a list of currently running containers on our system.

# docker ps -a
IT shows all containers on our system which is currently running , stopped or exited.

# docker run -p 8080:80 nginx 
* Port mapping allows us to access a service running inside a Docker container from the host machine.
* -p means Port 
* The -p flag is used to map a host port to a container port, allowing external access to services running inside Docker containers
* In Docker, port mapping allows us to access services running inside a container from the host machine. For example, in docker run -p 8080:80 nginx, the NGINX server runs on port 80 inside the container, and we map it to port 8080 on the host, so it can be accessed externally.


# docker run -d -p 8080:80 nginx 
* -d means detached mode , it means conatiner can run in background 
* If a container is running in foreground mode, the terminal gets blocked. To run another container in the same terminal, we must stop it first. Alternatively, we can use a new terminal or run containers in detached mode from the beginning.


# docker run -d --name mynginx -p 8080:80 nginx
* --name means given own choice name to container 
* HOST PORT : CONTAINER PORT (8080:80)
* To run multiple containers of the same application:
  - Container port remains the same (because app runs on fixed port)
  - Host port must be different (to avoid port conflict)

 - Example:
 - docker run -d -p 8080:80 nginx
 - docker run -d -p 8081:80 nginx
 - docker run -d -p 8082:80 nginx


# docker pull embarkx/hello-spring:latest

* docker pull → used to download an image from Docker Hub (registry)

* embarkx/hello-spring → image name
  - embarkx → repository/username
  - hello-spring → image name

* latest → tag (default version of the image)

* This command downloads the Docker image from Docker Hub to the local system

# docker stop conatiner-id/ conatiner-name
This commands help to stop the running docker container

# docker rm conatiner_id / container_name
This command help to delete the conatiner from your machine

# docker image rm image_name/image_id
This commands help to delete the image from your machine


# Docker container lifecycle 
Create - Start - Stop - Restart - Remove

# docker create --name app1 -p 3000:3000 embarkx/hello-python
This command helps to create container 

# docker start app1
This command help to run the container 

# docker stop app1 
This command helps to stop the conatiner which name is app1 if it is running 

# docker restart app1
This command helps to restart the conatiner which name is app

# docker remove app1 
This command helps to remove the conatiner which name is app

# docker pull embarkx/hello-node:v1.0.0
* Docker images assigned after : version assigned like v1.0.0
* latest version is not good for production 

# docker logs container_id
docker logs is used to view the output (logs) of a container

# docker logs -f container_id
Show me the logs of this container and keep updating them in real time.


#  docker exec -it c33bba49c1ca2fab4bf23f5002fb543a6ed19825faa4737fa3ea6ead6ad40f50 sh
* It is used to enter inside a running container and execute commands in its terminal
* docker exec -it helps you go inside a running container and run commands.


# docker images
It shows the all the iamges which is installed in system


# docker container prune
This commands will remove all the stopped conatiner from system 

# docker ps -aq
This commands give all currently running conatiner id

# docker images -aq 
This commands give all images 

# docker build -t tagname .
This comamnds helps to build the docker images from current folder with proper tag name like ( docker build -t myapp . )

# docker push username/docker_image_name
This commands helps to push on docker hub
