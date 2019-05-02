
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
