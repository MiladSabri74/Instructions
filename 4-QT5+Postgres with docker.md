# QT5+Postgres with docker

## Create Network

1- create network to connect container , here we called it test
```
sudo docker network create test
```

2- check network that was created or not 

```
sudo docker network ls
```

## Optional for Monitoring

in Tmux you can divide the terminal and in one of the pane monitor the stats of containers

```
sudo docker stats
```

## Prepare PostgreSQL

1- Run postgres container in test network also the data is stored into localhost

```
 sudo docker run --rm --name postgres-test -e POSTGRES_USER=postgres \
-e POSTGRES_PASSWORD=postgres --network test -v /data:/var/lib/postgresql/data -d \
ubuntu/postgres
```

## Prepare QT5

1- for first time you need to get images that can compile qt5 code, I use this image, you can use other or create ypur own image
(the size of image is about 900Mb)

```
sudo docker pull fstlx/qt5:ubuntu18
```

2- Run QT5 

```
sudo docker run --name qt5 -it --rm --network test -v /home/novin/Projects/Temp/db/test/testDB:/usr/src/app  fstlx/qt5:ubuntu18 /bin/bash 
```
Points : 
*  I called container qt5 with --name
*  I can interaction with container with -it
*  after exit from container, the container remove itself with --rm
*  container use network that was created before with --network
*  I defined a volume that path /usr/src/app in container will be sync with path /home/novin/Projects/Temp/db/test/testDB in my host
*  and finally I used fstlx/qt5:ubuntu18 images and run /bin/bash to access the terminal

Points for developing
*  in the container you should go to the /usr/src/app and see the codes
*  Run this command to make project
      ```
      qmake && make
      ```
*  Then run the execute file(for example: testDB in my system)
      ```
      ./testDB
      ```
*  In the code for setting the postgres host you should write the container name of postgres to connected to each other
   (here the name of postgres container is "postgres-test" so I use this against localhost or ip of postgres server



