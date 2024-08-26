# Docker

## Install Docker on Ubuntu

1- Set up Docker's apt repository.

```
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

2- Install the Docker packages.

```
 sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
3- Verify that the Docker Engine installation is successful by running the hello-world image.

```
 sudo docker run hello-world
```
## Usefull docker commands
 
 __before each command type *sudo docker* and then command__

| Raw |command   | Description    |
| :-----: | :---: | :---: |
| 1 | ps| list running conatiners   |
| 2 | ps -a|  list all conatiners |
| 3 | images|  list all images |
| 4 | stats|  list running conatiners and show the stats of usage |
| 5 | rm -f  <container-name/id> |  remove specific container |
| 6 | rmi -f  <image-name/id> |  remove specific image |
| 7 | pull  <image-name> |  download specific image form docker hub |
| 8 | run  <container-name/id> |  run specific container |
| 9 | start  <container-name/id> |  start specific container that is not running |
| 10 | stop  <container-name/id> |   stop specific container that is running |
| 11 | container cp  <source path> <dest path> | copy file between container and OS |
| 12 | network ls | list of networks in docker |
| 13 | port <container-name/id> | list of ports use in container |


