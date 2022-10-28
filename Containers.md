# Container File

- To automate container builds. What we want in our container image.


# Container management

### General Commands

- podman container list –all

### Running Containers

- podman run -d -p 8080:80 --name nginxtest  nginx:latest

- **Remove Container**
	- podman rm "containerid" 
- **Remove Image**
	- podman image rm "imageid"    
- podman stats 
- podman diff

# Container Network

- podman network list
- podman network inspect
- podman network inspect bridge


# Storage

## Local persistant volume storage 

- In Podman the local volumes are created in the home directory   
- podman volume create myvol 
- podman volume inspect myvol

## NFS

- podman volume create --driver local --opt type=nfs --opt o=addr=192.168.122.36,rw --opt device=:/nfsdata nfsvol   
    -   Run a container that uses that NFS storage.   
        -   podman run -it --name voltest2 --rm --mount source=nfsvol,target=/data nginx sh