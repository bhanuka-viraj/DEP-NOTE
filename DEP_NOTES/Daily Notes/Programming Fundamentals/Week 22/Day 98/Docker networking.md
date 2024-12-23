There are three default networks 
 =>bridge
 =>host
 => none

bridge -> Two containers can be connected mutually. 
host -> container connect with the os network.
none -> cannot connect, isolate

commands -> 

`docker network ls` -> to list the network
`docker network create -d <driver><name>` -> to create network
`docker network rm <name>` -> to remove network
`docker run --network bridge/host/none/<network name> image:tag` -> to switch between networks

![[Pasted image 20240719143251.png]]

