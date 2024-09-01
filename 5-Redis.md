# Redis

## Install Spcefic version Redis-Server

1- go to tmp
```
cd /tmp
```
2- go to this link <http://download.redis.io/releases/> and select your version then for example V7.4.0
```
wget http://download.redis.io/releases/redis-7.4.0.tar.gz 
```
3- extract file
```
tar zxf redis-7.4.0.tar.gz 
```
4- go to folder
```
cd redis-7.4.0
```
5- make redis
```
make
make test
sudo make install
```
6- config redis
```
sudo mkdir /etc/redis
sudo cp redis.conf /etc/redis
```
7- run the redis-cli and enjoy it :)
```
resdis-cli
```

