<h2 align="center">Docker commands</h2>

### Working with hub.docker
#### Docker Login
```shell
docker login registry...
```
#### Docker Logout
```shell
docker logout
```
#### Push a local image to hub.docker.com
```shell
docker push bscpaz/hello-world
```

### Showing your containers
 
| Command | Description |
| --- | --- |
| `docker ps` | List all actived containers |
| `docker ps -a` | List all containers |
| `docker ps -a -q` | List all containers by IDs |


### Creating and Executing images
#### Execute a new container and automatically remove it when it exits
```shell
docker run -rm bscpaz/hello-world:latest
```

#### Execute a new ubuntu container in interative and tty mode and then execute its bash
```shell
docker run -it --name ubuntu_1 ubuntu bash
```

#### Same of before but remove it when it exits
```shell
docker run --rm -it --name ubuntu_1 ubuntu bash
```

####  Execute a new bash container in dettached interative tty mode into "my-network" network
```shell
docker run -dit --name ubuntu_2 --network my-network bash
```

#### Execute a existing ubuntu container opening its bash
```shell
docker exec -it ubuntu bash
```

#### Execute a detached ubuntu in attached mode
```shell
docker attach ubuntu
```

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

### Building images
####  Build a image from a default Dockerfile in current directory (.)
```shell
docker build -t <image-name> .
```
#### Build a image from a specific Dockerfile (prod) in current directory
```shell
docker build -t <image-name> . -f Dockerfile.prod`
```

* Volumes

| Command | Description |
| --- | --- |
| `docker volume ls` | List all volumes |
| `docker volume rm $(docker volume ls -q)` | Remove non-used volumes. Note: execute `docker-compose down --volumes` first. |
| `docker volume inspect <id>` | Inspect a volume |
| `docker-compose down --volumes` | Remove volumes |




* Checking LOGs

| Command | Description |
| --- | --- |
| `docker logs <container-name>` | Remove (forced) a container |

### Docker-compose
#### Show only docker-compose's containers running
```shell
docker-compose ps
```
#### Up a docker-compose in detached mode
```script
docker-compose up -d
```
#### Up a docker-compose in detached mode rebuilding all images
```shell
docker-compose up -d --build
```
<hr>
<h4 align="center">Known issues</h4>

```
Issue: 
  Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?
Solution: 
  Run "sudo service docker start" on terminal
```

```
Issue: 
  After running docker-compose up --build, you get:
  "ADD failed: file not found in build context or excluded by .dockerignore: stat 'some file': file does not exist"
Solution: 
  You are operating from a subfolder of the root which the docker-compose file exists.
  Check your 'project:build:context' in docker-compose file and change it to "." context (the root, not a subfolder).
```

```
Issue: 
  Error response from daemon: manifest for netflixoss/zuul:latest not found: manifest unknown: manifest unknown
Solution: 
  That's because there is only one version 1.0.28 available for image netflixoss/zuul. 
  There is no default "latest" version for the image.
  Change your docker-compose file to "image: netflixoss/zuul:1.0.28"
```

```
Issue: 
  After running docker compose up -d --build, you get:
  "failed to solve: rpc error: code = Unknown desc = failed to solve with frontend dockerfile.v0: failed to read dockerfile: 
    open /var/lib/docker/tmp/buildkit-mount3381506098/Dockerfile: no such file or directory"
Solution:
  Add the extension of Dockerfile in docker-compose. Example:
    build:
      context: ./ms-desafio
      dockerfile: Dockerfile >>> Dockerfile.yaml
```

```
Issue: 
 /bin/sh: ./mvnw: not found.
Solution:
  Change the encode's file of mvnw to "LF".
