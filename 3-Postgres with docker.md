# Postgres with docker

In this file we explain how to use postgres in docker (we use ubuntu 18.04)

## Prepration

1- get image from docker hub (latest tag)

```
sudo docker pull ubuntu/postgres
```

2- check the images list

```
sudo docker images
```
3- Now run the container to use postgres

```
sudo docker run --name postgresql-test -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=postgres -p 5432:5432  -v /data:/var/lib/postgresql/data -d ubuntu/postgres
```

| Raw | tag  |  Parameter | Description    |
| :-----: | :---: | :---: |:---: |
| 1 | --name|   postgresql-test | set name to the container for use in future against id-container   |
| 2 | -e POSTGRES_USER|postgres   |  username of database you want to login  |
| 3 | -e POSTGRES_PASSWORD | postgres   | password of database you want to login   |
| 4 | -p | 5432:5432   | map docker port to local os port / first for docker and second for OS |
| 5 | -v | /data:/var/lib/postgresql/data  |set volume first path is in docker and second is in local server to store data    |
| 5 | -d |  ---  |  run on background  |

4- (Optional) for use commandline of psql after run container use this

```
sudo docker exec -it postgresql-test bash
```

__Point__ : -it is for terminal of docker that let you send and recieve from terminal

__Point__ : bash is the app that you want to execute from container

__Point__ : postgresql-test is the name of container


5- (Optional) you can start or stop current container with this commands

```
sudo docker start postgresql-test
```
```
sudo docker stop postgresql-test
```
6- (Optional) I use this script to start postgres container ( in this script at first I stop service of postgre in local)

```
#!/bin/bash

# Stop PostgreSQL service on the host
echo "Stopping PostgreSQL service on the host..."
sudo systemctl stop postgresql.service

# Add a delay before starting the Docker container (e.g., 5 seconds)
echo "Waiting for 5 seconds before starting the Docker container..."
sleep 5

# Check if the PostgreSQL service was stopped successfully
if systemctl is-active --quiet postgresql.service; then
    echo "Failed to stop PostgreSQL service on the host."
    exit 1
else
    echo "PostgreSQL service stopped successfully."
fi

# Start the PostgreSQL Docker container
echo "Starting PostgreSQL Docker container..."
sudo docker start postgres-test

# Check if the Docker container started successfully
if [ $? -eq 0 ]; then
    echo "PostgreSQL Docker container started successfully."
else
    echo "Failed to start PostgreSQL Docker container."
    exit 1
fi

```
