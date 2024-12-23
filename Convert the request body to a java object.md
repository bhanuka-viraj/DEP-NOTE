->First add the `jackson-databind` dependency to the pom.xml file

-> Create the to classes related the the request body
![[Pasted image 20240831003621.png]]

-> pass the instance of to class to the handler method in controller. 

![[Pasted image 20240831004623.png]]

-> Add the `@EnvableMvc` annotation if it is not added to the config class