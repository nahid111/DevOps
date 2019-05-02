&diams; Create files
```bash
$ touch .0 1 2
$ mkdir foo
$ touch foo/3 foo/4 foo/5
$ tree -a
```
<br>&diams; Run Container
```bash
$ docker run -d --name enginx nginx
```


## Copy files/directories from host to a Docker container
```bash
$ docker cp . container_name:/tmp/
$ docker exec -it container_name bash -c 'tree -a /tmp/'
```
## Copy files from Docker container to your host
```bash
$ docker cp container_name:/tmp/. .
$ tree -a
```



<br><br>
