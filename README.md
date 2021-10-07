<h1 align="center">Docker/Linux commands</h1>
<p align="center">This page shows docker's or linux commands.</p>

<h2 align="center">Docker commands</h2>

* Working with hub.docker
 
| Command | Description |
| --- | --- |
| `docker login` | Docker Login |
| `docker logout` | Docker Logout |
| `docker push bscpaz/hello-world` | Push a local image to hub.docker.com |


* Showing your containers
 
| Command | Description |
| --- | --- |
| `docker ps` | List all actived containers |
| `docker ps -a` | List all containers |
| `docker ps -a -q` | List all containers by IDs |


* Creating and Executing images

| Command | Description |
| ------ | --- |
| `docker run -rm bscpaz/hello-world:latest` | Execute a new container and automatically remove it when it exits |
| `docker run -it --name ubuntu_1 ubuntu bash` | Execute a new ubuntu container in interative and tty mode and then execute its bash |
| `docker run --rm -it --name ubuntu_1 ubuntu bash` | Same of before but remove it when it exits |
| `docker run -dit --name ubuntu_2 --network my-network bash` | Execute a new bash container in dettached interative tty mode into "my-network" network |
| `docker exec -it ubuntu bash` | Execute a existing ubuntu container opening its bash |
| `docker attach ubuntu` | Execute a detached ubuntu in attached mode |

Note: without expliciting the `--network`, the containers cannot communicate between them by theirs names. Just by theirs IPs.


* Create and execute a detached new nginx server with a mounted directory
```
docker run -d -p 8080:80 --name nginx \
      --mount type=bind,source="$(pwd)"/docker/volume/nginx/html,target=/usr/share/nginx/html nginx
```

* Execute a image replacing the Dockerfile's CMD command.
  * ENTRYPOINT is immutable command. 
  * CMD provides parameteres to ENTYPOINT command.
  * What comes after image's name replaces the Dockerfile's CMD command.
```
docker run --rm bscpaz/hello-world:latest echo "hello, Bruno"
```

* Workding with existing containers
 
| Command | Description |
| --- | --- |
| `docker start <image-name>` | Start an existing container |
| `docker stop <image-name>` | Stop an existing container |

* Removing containers

| Command | Description |
| --- | --- |
| `docker rm bscpaz/hello-world -f` | Remove (forced) a container |
| `docker rm $(docker ps -a -q) -f` | Remove (forced) all containers in just one command |


* Working with networks

| Command | Description |
| --- | --- |
| `docker network ls` | List all docker's network |
| `docker network inspect <network>` | Inspect a docker network. i.e: "bridge" |
| `docker network create --driver bridge my-network` | Criate a "bridge" network named as "my-network" |
| `docker network connect my-network ubuntu_1` | Connect an existing container into an existing network |
| `docker network prune` |Remove all custom networks not used by at least one container |

<br><br>
<h2 align="center">Linux commands</h2>

* Files

| Command | Description |
| --- | --- |
| `mv file1.txt file2.txt` | Rename a file |


* IPs
 
| Command | Description |
| --- | --- |
| `apt update && apt install iproute2 -y` | Install IP package with confirmation |
| `apt-get update && apt-get install iputils-ping -y` | Intall PING package with confirmation |
| `ip addr show` | Shows the IP of current linux |


* Unzip

| Command | Description |
| --- | --- |
| `sudo apt-get install unzip` | Install Unzip package |
| `sudo unzip path/filename.zip -d another_path_or_same_path` | Unzip a zip file from one directory to another. -d = directory |


* JDK

| Command | Description |
| --- | --- |
| `sudo apt install default-jdk` | Install JDK |


* WEB

| Command | Description |
| --- | --- |
| `apt-get update && apt-get install curl -y` | Install curl (client URL) |
| `curl http://localhost` | Check client URL connectivity |
| `curl http://host.docker.internal:8080` | A docker container accessing a service (8080) in the host machine (my machine) |
