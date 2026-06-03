
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
* In Docker, port mapping allows us to access services running inside a container from the host machine. For example, in docker run -p 8080:80 nginx, the NGINX server runs on port 80 inside the container, and we map it to port 8080 on the host, so it can be accessed externally