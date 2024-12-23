![[Pasted image 20240722184653.png]]

Host network is used to connect the app and the MySQl 

run this command to create a docker container from mysql -> 
`docker run -e MYSQL_ROOT_PASSWORD=mysql --network=host mysql`

==Change the port of the mysql if the default already in used -> ==
`docker run --name kajja -e MYSQL_ROOT_PASSWORD=mysql -e MYSQL_TCP_PORT=3307 mysql`

How to detach terminal from the process
`docker run --name kajja -e MYSQL_ROOT_PASSWORD=mysql -e MYSQL_TCP_PORT=3307 -d mysql` -> 
this detach the terminal 

How to show logs -> 
`docker logs <container name | containe hash>`

How to attach terminal to the process -> 
`docker attach <container name | container hash>`

How to get the all containers id -> 
`docker ps -a -q`

To delete all docker containers  -> 
`docker remove -f $(docker ps -a -q)`

How to  get the information about a container 
`docker inspect <container id (hash | name)>`

[[How to create a MYSQL data base using intellij IDEA]]
