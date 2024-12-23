step1 -> add dependencies for hibernate

step2 -> create persistance.xml file

go to project Structure ->
![[Pasted image 20240710184549.png]]

The move the MET.INF to the resource directory.

step3 -> 

config the persistence.xml file
![[Pasted image 20240711021420.png]]
`In here persistence-unit means the entity manager factory`

step 4 ->

Create the util class (this is a singleton class)
![[Pasted image 20240711021900.png]]

when execute the `buildEntityManagerFactory()` properties are taken from the `persistence.xml` file and create the entityMangerFactory

Step -> 5
getting the EntityMangerFactory and Create the EntityManger

![[Pasted image 20240711023243.png]]
