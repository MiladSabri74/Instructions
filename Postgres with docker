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

| Raw | tag  |Parameter | Description    |
| :-----: | :---: | :---: |
| 1 | --name|   postgresql-test | set name to the container for use in future against id-container   |
| 2 | -e POSTGRES_USER|postgres   |  username of database you want to login  |
| 3 | -e POSTGRES_PASSWORD | postgres   | password of database you want to login   |
| 4 | -p | 5432:5432   | map docker port to local os port / first for docker and second for OS |
| 5 | -v | /data:/var/lib/postgresql/data  |set volume first path is in docker and second is in local server to store data    |
| 5 | -d |  ---  |  run on background  |
