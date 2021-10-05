<h1 align="center">Docker commands</h1>
<p align="center">This page shows docker's commands.</p>


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

* Remove (forced) all containers in just one command
```
docker rm $(docker ps -a -q) -f
```

* Create a new nginx server with mount directory
```
docker run -d -p 8080:80 --name nginx --mount type=bind,source="$(pwd)"/docker/volume/nginx/html,target=/usr/share/nginx/html nginx
```
