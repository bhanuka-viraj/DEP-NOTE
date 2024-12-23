
|                                                                                  |                                                                                                                                                                                                                                                                                                                                                                                |
| -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| What is the <br>transaction context                                              | The transaction context refers to the environment in which a transaction is managed, ensuring that a series of operations are executed as a single unit of work, either all successfully completing or all failing, to maintain data integrity and consistency.                                                                                                                |
| Which CRUD operation<br>are required tranasaction context                        | Excluding Reading operation all other operations should be done inside a transaction context in JPA                                                                                                                                                                                                                                                                            |
| What happened if the <br>entity class is not defined in the <br>persist.xml file | In JPA all the database is scanned to find the entity <br>class if the entity class is not defined.So defining the entity class is a good practice                                                                                                                                                                                                                             |
| What does JPA use  between<br>regular and prepared<br>statement                  | Only use perpared statement                                                                                                                                                                                                                                                                                                                                                    |
| How to get the log of <br>the SQL LOg in <br>JPA                                 | ![[Pasted image 20240711114658.png]]<br><br>set the property `hibernate.show_sql` true<br><br>This is reduce performace in production leve because it<br>give time to show the SQL. This is only use in development.It is not a good practice use in the production level                                                                                                      |
| how to format the SQL<br>log                                                     | ![[Pasted image 20240711114943.png]]<br><br>set the `format_sql` property true                                                                                                                                                                                                                                                                                                 |
| what is the difference<br>between `persist`<br>and `save`                        | return types -><br>`Persist(entity):void` -> void<br>`Save(entity):Serializable` -> new added record primary key<br><br>when primary key is auto increment and user try to give<br> a id when execute persist, it gives a error. But Save ignore the given id and generate the new id.No error<br> <br>Persist is found in the JPA and Save is found in the native<br>language |
| How to create                                                                    | use `persist(entity)`                                                                                                                                                                                                                                                                                                                                                          |
| How to read                                                                      | use `find(entity class objct, pk):entity` this return the entity class object<br><br>`getRefernce(entityClass objct, pk):entity`<br>                                                                                                                                                                                                                                           |
| how to delete                                                                    | use `remove(entity /proxyentity):void`                                                                                                                                                                                                                                                                                                                                         |
| how to update                                                                    | [[Dirty Checking Feature]]                                                                                                                                                                                                                                                                                                                                                     |

To find the properties of the persintance.xml file -> 
https://docs.jboss.org/hibernate/orm/6.5/userguide/html_single/Hibernate_User_Guide.html#settings-jdbc

How to create -> 

![[Pasted image 20240711122516.png]]

How to read -> 
![[Pasted image 20240711122444.png]]


|                                                               |                                              |
| ------------------------------------------------------------- | -------------------------------------------- |
| What would return if non exist<br>entity is find()            | null is return. No error message is show<br> |
| what would happen above case<br>when use the `getReference()` | `EntityNotFoundExcetption` is thrown         |
|                                                               |                                              |
[[What is the difference between find( ) and getReference( )]]

How to delete -> 

![[Pasted image 20240711130723.png]]

 How to update -> 
 There is no special api for updating. Update is done using [[Dirty Checking Feature]]
 
![[Pasted image 20240711131714.png]]
[[Persistence Context]]
