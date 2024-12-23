to get the keys for resource bundle ->
https://docs.jboss.org/hibernate/orm/6.5/userguide/html_single/Hibernate_User_Guide.html#settings-jdbc

repeat the previous step up to the persistance.xml. And add this changes ->

only set the persistence-unit name and the provider

![[Pasted image 20240710191919.png]]

Step 2 ->

create a resource bundle
![[Pasted image 20240710192026.png]]

step 3 -> 
create util class

![[Pasted image 20240711023155.png]]
To create the EntityManagerFactory, properties of the application.properties files are needed. Those properties are getting using the appliation.properties file and then added to the properties instance and it is used to create the EntityManagerFactory






