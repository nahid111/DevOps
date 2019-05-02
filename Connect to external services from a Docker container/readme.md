
## Connecting to remote services
- Launch a MySql Docker-Container on a Remote-Server
- Connect to the remote MySql service from a local Docker-Container
<br>
&diams; Run a MySQL Docker-Container in a remote server

    $ docker run -d -p 1000:3306 --name mysql-cont -e MYSQL_ROOT_PASSWORD=my-secret-pw mysql

&diams; Check connection 

    $ mysql -h 127.0.0.1 -P 1000 -u root -p

&diams; Check connection from local

    $ sudo apt install mysql-client
    $ mysql -h 35.171.151.164 -P 1000 -u root -p

&diams; Run a local MySQL Docker-Container and connect to the Remote mysql server

    $ docker run -it mysql mysql -h 35.171.151.164 -P 1000 -u root -p

<br><br>
## Connect to other containerized services
- Launch a MySql Docker-Container
- Launch an Alpine Docker-Container and connect to MySql


```bash
$ docker network ls

# create a custom network
$ docker network create --driver bridge my_network

# Run server
$ docker run --name mysql_server -d -p 3307:3306 --network my_network -e MYSQL_ROOT_PASSWORD=password mysql

# Run client in the same network of the server
$ docker run --rm --name my_client -it --network my_network alpine ping mysql_server`
```
