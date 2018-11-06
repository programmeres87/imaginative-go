# Imaginative Go (Work in Progress)
## What is this?
Imaginative Go is a collection of free code samples in the form of Go web application.

We believe that when learning programming language is by directly implement the knowledge into a project. This imaginative project will show doing web application in Go language as well as other samples that not related to web. We don't use any framework and forgive us if the code still not efficient or optimal, since this project will just give you an idea how to achieve something in Go language.

## Why Imaginative Go?
- Ideas about achieve something with Go language
- Plenty of working code samples
- Easy to run (with or without Docker, personally I prefer with Docker)
- You can contribute

## Requirements
- Docker Engine (version 17.03.0 or later)
- Docker Compose (version 1.22.0 or later)

Docker is used since it will create additional service to mimic realistic web sample. Imaginative Go is using MySQL and MongoDB with pre-populated data. It's useful to show code that doing query to those database service (SQL and noSQL).

For those who need documentation of Docker installation, please refer to [Docker CE](https://store.docker.com/search?type=edition&offering=community) and [Docker Compose](https://docs.docker.com/compose/install/)

## Usage
#### Linux/MacOS
Just do this.

```
git clone https://github.com/sonyarianto/imaginative-go.git
cd imaginative-go
sudo docker-compose up
```

After that, go to your browser and type
```
http://localhost:9899
```
or
```
http://<YOUR_LOCAL_IP_ADDRESS>:9899
```
or
```
http://<YOUR_DOCKER_MACHINE_IP_ADDRESS>:9899
```
#### Note 1
To recreate all containers you can type
```
sudo docker container stop mysql_imaginative_go go_imaginative_go adminer_imaginative_go mongodb_imaginative_go

sudo docker container rm mysql_imaginative_go go_imaginative_go adminer_imaginative_go mongodb_imaginative_go
```
after that, type
```
sudo docker-compose up --build --force-recreate
```

#### Note 2
You can access the MySQL table using Adminer, go to this address
```
http://localhost:8989
```

#### Note 3
MySQL and MongoDB expose random port to host machine. You can see it by typing this after all containers are running.
```
sudo docker ps -f "name=mysql_imaginative_go" -f "name=mongodb_imaginative_go"
```
Sample output is like below
```
CONTAINER ID        IMAGE                    COMMAND                  CREATED             STATUS              PORTS                                NAMES
fffe82669408        imaginative-go_mongodb   "docker-entrypoint.s…"   3 minutes ago       Up 3 minutes        0.0.0.0:32774->27017/tcp             mongodb_imaginative_go
5efabed778f7        imaginative-go_mysql     "docker-entrypoint.s…"   3 minutes ago       Up 3 minutes        33060/tcp, 0.0.0.0:32773->3306/tcp   mysql_imaginative_go
```

## Docker Images Used
- mysql:latest (see docker-compose.yml for default credential, port exposed to host is using random port, see on docker ps command)
- mongodb:latest (see docker-compose.yml for default credential, port exposed to host is using random port, see on docker ps command)
- adminer (see docker-compose.yml for default mysql credential, port exposed to host at 8989)

## Credits
### Themes
- [Editorial](https://html5up.net/editorial) from [HTML5 UP](https://html5up.net)
- [Phantom](https://html5up.net/phantom) from [HTML5 UP](https://html5up.net)

## Contributors
- Sony Arianto Kurniawan - sony@sony-ak.com - original author, project maintainer
- Prasetyama Hidayat - prasetyama@gmail.com

## Screen Shot
### Home Page
![Imaginative Go - Screenshot 1](/src/assets/images/screenshot1.png?raw=true "Imaginative Go - Screenshot 1")
### Sample Code List
![Imaginative Go - Screenshot 2](/src/assets/images/screenshot2.png?raw=true "Imaginative Go - Screenshot 2")
