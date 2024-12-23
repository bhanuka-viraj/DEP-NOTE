
|                                                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Does JPA only works with RDBMS                                        | Yes. JPA only works with  RDBMS                                                                                                                                                                                                                                                                                                                                                                                                                   |
| What is Hibernate                                                     | HIbernate is a implementation list. They got a famous<br>implementation for JPA called `HibernateJPA Impl`. <br>It is a part of a `Hibernate ORM`<br><br>Hbernate also got a implementation for  <br>`Jakarta Bean validation` called `Hibernate validator impl`<br><br>==Hibernate is a implementation for Jakarta Persistence API==<br>                                                                                                         |
| What is <br>`Hibernate ORM`                                           | Got two parts -> <br><br>1.Native HIberate<br>2. HIbernate JPA Impl                                                                                                                                                                                                                                                                                                                                                                               |
| What is `ORM`                                                         | `ORM` -> Object Relational Mapping<br><br>Object-relational mapping (ORM) is a technique that facilitates seamless interaction between object-oriented programming languages, like Java, and relational databases by automatically mapping objects to database tables.                                                                                                                                                                            |
| what is the <br>spec for <br>no SQL database                          | Jakarta NoSQL                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| What is JPA                                                           | JDBC Api is wrapped up by the JPA                                                                                                                                                                                                                                                                                                                                                                                                                 |
| what are the implmemetation<br>for the JPA                            | -> HIberante <br>-> Eclipse <br>-> Open JPA<br>                                                                                                                                                                                                                                                                                                                                                                                                   |
| What is the <br>relationship <br>between JPA and<br>Native hiberanate | Native hibernate is a extension for the JPA. Native hibernate got some API that do not have JPA. So using <br>native hiberanate is coupled project with the native <br>hibernate and hard to migrate to a another JPA implementaion. So industry not tend to use Native hibernate<br><br>![[Pasted image 20240711015109.png]]<br>Both JPA and Native language does not have the direct access to the JDBC. Native language have access to the JPA |
| What is a entity                                                      | Entity is a instance that created by the class. This is the class that is mapped with the relations(Tables)<br><br>![[Pasted image 20240710165349.png]]<br><br>Table are mapped with the classes<br>Rows are mapped with the entity                                                                                                                                                                                                               |
| Define terms                                                          | SQL -> Structured Query Language<br>JPQL -> Jakarta Persistance Query Language<br>HQL -> Hibernate Query Language                                                                                                                                                                                                                                                                                                                                 |
| what is the <br>architecture of<br>Hibernate <br>                     | ![[Pasted image 20240710165934.png]]                                                                                                                                                                                                                                                                                                                                                                                                              |

![[Pasted image 20240710170123.png]]


|                             |          |
| --------------------------- | -------- |
| what does mean<br>bootstrap | starting |
|                             | <br><br> |
What is the objective of using bootstrap in the hibernate

To create ->
Entity Manager Factory  
Session Factory Manager

There are two bootstrap in hibernate
1.Jakarta persistence bootstrap
2.Native Hibernate bootstrap

![[Pasted image 20240710174127.png]]

|                                               |                                         |
| --------------------------------------------- | --------------------------------------- |
| What is the use <br>of factory                | to encapsulate the object creation      |
| What is the use<br>of EntityManger<br>Factory | to produce EntityManager implementation |
| What is the use<br>of session Factory         | to produce Session implementation       |


![[Pasted image 20240711015202.png]]

Since EntityManger Factory and the SessionFactory produce the same product, now create a one factory call SessionFactoryImpl

==Note ->==
When session impl is seen under the shape of the Session, then it can be accessed to the all method of session and the Entity Manger. When session impl Is seen under the shape of the Entity Manager only allowed to accessed the method of Entity Manager. This is how JPA and the Native are changed.

|                                                        |                                                                                                                                                                        |
| ------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| How to create a sessionFactory<br>impl                 | We cannot create sessionFactoryImpl directory.<br>When we give the input sessionFactoryImpl<br>is given<br><br>Then sessionFactoryImpl can create the <br>session impl |
| How to give the data to create<br>session factory impl | Using XML <br>Using Resoruce Bundle                                                                                                                                    |
| What is a persistence unit                             | EnitiyManager Facotry                                                                                                                                                  |
| What is persistence context                            | EntityManger                                                                                                                                                           |

[[How to create EntityManager using XML]]
[[How to create entityManager using resource bundle]]
[[How to create Session using XML]]
[[How to create Session using resource bundle]]
[[How does the Util class works as  a singleton]]
