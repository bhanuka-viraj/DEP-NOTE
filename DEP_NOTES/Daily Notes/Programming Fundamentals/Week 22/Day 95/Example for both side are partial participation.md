This example about a dating app. This has unary relationship. Both side has partial participation. There are two methods to solve this. One is using a associate table and other doing without a associate table. Using associate table is thee perfect way to do this. Because other method got some disadvantages like having null values, required to set the relationship between both side (this is happen because this example is a unary relationship)

![[Pasted image 20240716134428.png]]



![[Pasted image 20240716135221.png]]

==Method 1 ->== without associate table

data base query -> Refer how to create ENUM in postgre sql

![[Pasted image 20240716135452.png]]

How to use the ENUM with entity class

Use `@Enumerated` annotation to set the ordinal type string or number
![[Pasted image 20240716141103.png]]

How to set the enum in to the postgresql ->

add the url to this

![[Pasted image 20240716143905.png]]

![[Pasted image 20240716143829.png]]


Since this is a unary relationship the relationship should be added to both of them

![[Pasted image 20240716144449.png]]

==Method 2 ==-> 

![[Pasted image 20240717221005.png]]

user class -> 
![[Pasted image 20240717112433.png]]

partner class (associate table)
![[Pasted image 20240717112507.png]]

demo class 
![[Pasted image 20240717112533.png]]

With this it is allowed to the same relationship using the same user in difference order and the same user with the another  user. Those cases are handled through the application. This is happened because the relationship is unary.

==When there is no attributes in the associate entity==

There is another way to do this if there is no attributes in the relationship


|                                       |                                                                                                                                                                |
| ------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the use of <br>`@JoinTable()` | This can be used to keep associate table without creating <br>a separate relation for it. to do this there should be no <br>attributes in the associate entity |
User class -> 

![[Pasted image 20240717114441.png]]

how to add users and set partners

![[Pasted image 20240717114858.png]]

how to remove partners 

![[Pasted image 20240717115127.png]]