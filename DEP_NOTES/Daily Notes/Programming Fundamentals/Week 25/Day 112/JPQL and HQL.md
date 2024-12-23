JPQL -> Java Persistence Query Language 
HQL -> Hibernate  Query Language 


Note -> Everything that can be done using SQL cannot be done using the JPQL or HQL.  There is a relationship between HQL and JPQL. Everything in JPQL is found in the HQL but Some api of HQL are not found in the JPQL

![[Pasted image 20240808235539.png]]

|                                                 |                                                                      |
| ----------------------------------------------- | -------------------------------------------------------------------- |
| What does native query<br>means in JPQL and HQl | The queries that  written using the SQL in ORM in JPA or N.H<br><br> |
|                                                 |                                                                      |
![[Pasted image 20240808235559.png]]


Note -> This is a Class hierarchy of the native hibernate and JPA . The difference between Query in the the JPA and the Native hibernate is  Query of the native hibernate is a generic interface

==API in JPA and Native Hibernate== => 

![[Pasted image 20240809000137.png]]

==API in Query== => 

![[Pasted image 20240809001017.png]]

==API in TypedQuery `<T>`== =>

![[Pasted image 20240809001125.png]]

==API in Query `<T>`== =>

![[Pasted image 20240809001956.png]]


|                                                                                                                  |                                                                                                                                                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| What is the difference <br>between `getSingleResult()`<br>in `Query` and <br>`uniqueResult() : T` in  `Query<T>` | when there is no value to return as return `getSingleResult()` return `NoResultExceptoin`<br>and `uniqueResult() : T`  return the null<br><br>both return the `NoUniqueResultExceptoin`<br>when  there are multiple result.(more than one) |
| What is the return of the <br>`getResutlList` and the <br>`list()`                                               | object array                                                                                                                                                                                                                               |


Explain this -> This return as object array
![[Pasted image 20240809002414.png]]

![[Pasted image 20240809002432.png]]
This return the object arrays that contains the details of the customer.


Explain this => This return as a customer list
![[Pasted image 20240809002912.png]]
When result type is specified, it return the result type object. In this case it return the customer objects



![[Pasted image 20240809002925.png]]


Explain this => 

This return a tuple (A tuple is a class that is created in the JPA)
Tuple can be used by both index and the name. This is usually used when the Return type is difficult to specified.
![[Pasted image 20240809003335.png]]

![[Pasted image 20240809003350.png]]

