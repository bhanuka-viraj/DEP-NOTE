doc for postgresql library -> 
https://node-postgres.com/

what does mean client -> 

![[Pasted image 20240813115812.png]]
client means new connectivity

How to connect and run a query in postgresql in NodeJs

==step 1 ==-> 
![[Pasted image 20240813120515.png]]

==step 2== ->
 to the connect the client 
![[Pasted image 20240813121455.png]]

==step 3== -> 
to do the query 

![[Pasted image 20240813121519.png]]
note -> This does not work as a prepared statement. There is no SQL injection in here.

==step 4== -> 
end the client

![[Pasted image 20240813121628.png]]

NOTE -> 
This is used for the insert 100 difference data. But every time execute the inset in query. This is need to be worked as parameterized query.Compile one get the values as arguments 

This work as a a parameterized statement 
![[Pasted image 20240813125110.png]]
