![[Pasted image 20240711184212.png]]

![[Pasted image 20240711184226.png]]

when set the name dirty flag is turned to true. Now this is eligible to update. But when refresh another select query is executed and sync the managed state element with the values in the database. Now dirty flag is turned into false again and update not gonna happen

==In JPA dispatch state element cannot be used with refresh( ) but in native it can be done. ==
