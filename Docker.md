# Docker Cheatsheet
---

## Basic commands

### Login to Docker
``docker login``
To be able to pull images or push images to hub.docker.com you must login first.

### List containers
``docker container ps``
List running containers.

``docker container ps -a``
List all containers.

---

## Working with images

### List images
``docker images``
You can also do, ``docker image ls``.

### Inspect image
``docker image inspect image-id or image name``

### Tag image
``docker image tag nginx:latest nginx:version1``  

### Push image
First you need to tag your image with your username for hub.docker.com and then the repo name.
``docker image tag nginx:latest alibabis/nginx``
The username for Docker Hub is alibabis, and the repo that's created is nginx. Let's push this image.
``docker push 1980is/nginx``

### Image history
To see the image layers.
``docker image history nginx``

---

## Working with containers

### Run container
``docker container run -dit --name fedora-v1 fedora``
-d stands for detached mode. -i stands for interactive and -t stands for terminal. --name names the instance, you don't have to provide a name, then Docker will create a random name for the container. Fedora without any tags behind it, e.g., fedora:36, mean that Docker will pull the latest Fedora image, the equivalent of writing fedora:latest.

``docker container run --name webserv2 -d -p 9002:80 nginx``
This runs an nginx container named webserv1 in detached mode on port 9002. To check it out run http://localhost:9002/ in your brow

### Connect to a running container
`` docker exec -it fedora-v1 bash``
To disconnect from the container write ``exit``.

### Stop container
``docker container stop fedora-v1``

### Kill container
``docker container kill fedora-v1``
When stopping doesn't work, you can kill the container.

### Remove containers
This command removes **all** stopped containers.
-a stands for all containers. -q returns only the container id.
``docker container ps -aq | xargs docker rm``

---

## Debug

### Inspect container
``docker container inspect fedora-v1``
See container information. You can use the container name or container id.
``
### View container logs
``docker container logs fedora-v1``


---