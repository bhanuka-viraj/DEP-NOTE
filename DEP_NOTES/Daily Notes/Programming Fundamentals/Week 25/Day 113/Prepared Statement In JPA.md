What is the difference between prepared statement in JDBC and JPA

-> JDBC not allowed to use naming parameters but JPA allow this. JDBC only allow positioning paramters JPA support both name and position parameters

->JDBC not allowed to specify the index in the position parameter but JPA allow

This how done in JDBC

![[Pasted image 20240809124936.png]]
This how done in JPA using the specify the position 

![[Pasted image 20240809125410.png]]

What are the rules for the position specifying ->

-> Need to be start from the 1 (this not applicable for the Hibernate 5)
-> Cannot to have a gap between numbers (cannot use 1 and 100)
-> order of the parameters is not concerned
-> Also can used without explicit specifying

![[Pasted image 20240809130038.png]]

NOTE -> JPA also use the JDBC as the underline technology


How to use this with the naming parameters 
 ![[Pasted image 20240809130144.png]]
 

==Q.== Is it allowed to use both naming and positioning in the same time (mixing)

==A.==

![[Pasted image 20240809130501.png]]

Yes. It is allow to mix positioning and naming parameters in the same time. But this is not considered as a best practice.

![[Pasted image 20240809130512.png]]