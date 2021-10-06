<h1 align="center">Docker commands</h1>
<p align="center">This page shows docker's commands.</p>


* Login/Logout into DockerHub
```
docker login
docker logout
```

* List all actived containers
```
docker ps
```

* List all containers
```
docker ps -a
```

* List all containers by IDs
```
docker ps -a -q
```

* Execute a image without registering as a container
```
docker run -rm bscpaz/hello-world:latest
```

* Enter into a image in interative and tty mode
```
docker run -it --name ubuntu ubuntu bash
docker run --rm -it --name ubuntu ubuntu bash
docker exec -it ubuntu bash
```

* Create and execute a new nginx server with mount directory
```
docker run -d -p 8080:80 --name nginx \
      --mount type=bind,source="$(pwd)"/docker/volume/nginx/html,target=/usr/share/nginx/html nginx
```

* Execute a image replacing the Dockerfile's CMD command.
  * ENTRYPOINT is immutable command. 
  * CMD could provides parameteres to ENTYPOINT command.
  * What comes after image's name replaces the Dockerfile's CMD command.
```
docker run --rm bscpaz/hello-world:latest echo "hello, Bruno"
```

* Remove (forced) all containers in just one command
```
docker rm $(docker ps -a -q) -f
```
