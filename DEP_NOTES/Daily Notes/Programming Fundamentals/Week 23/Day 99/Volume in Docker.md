What is volume in Docker -> 

In Docker, a **volume** is a mechanism for persisting data generated and used by Docker containers. Volumes are stored outside the container's filesystem, allowing data to persist even when the container is removed. They are managed by Docker and can be used to share data between containers and with the host system.



How to map volume  in mysql data base when create a mysql container

`docker run --network host -e MYSQL_ROOT_PASSWORD=mysql -e MYSQL_TCP_PORT=3307 -v ~/mysql:/var/lib/mysql -d  mysql`

