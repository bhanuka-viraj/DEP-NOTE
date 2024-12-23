![[Pasted image 20240708114546.png]]

Complete code -> 

![[Pasted image 20240708122210.png]]


==Q.== How to customized the error messages in the validation -> 
==A.== Adding the error message with annotation that is used for the validation
use `@message` annotation

==Q.== How to add a regular expression for validation ->
==A.== Use `@Pattern`

![[Pasted image 20240708122909.png]]


==Q.== How to get the added error value for the error message 
==A.== Use `${validatedValue}` with the annotation
![[Pasted image 20240708123721.png]]
