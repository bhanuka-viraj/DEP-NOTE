There is only one rule for the many to many relationship. Any totally participation cannot be handled by the data base. Because database in default handle the many to many with the both side are partially participated.

Rule -> 
A associate entity is created taking the both side primary keys as the foreign keys and the create a composite primary key using both foreign keys. Total participation should be handled through the application. 

How to determine the Total or Partial -> 

This depend on the business logic. let's consider two entity Called A and B. If A cannot be created without B, then A should be total participation. Otherwise A is partial participation. Then A and B is connected as necessary

==When there is no attribute in the relationship==


Example -> 

![[Pasted image 20240723075250.png]]



![[Pasted image 20240722164417.png]]

When mapping without a separate entity class and there is only one totally participated side then that side is considered as the Owner and. If the both side are totally participated or partially participated then one side can be defined as the owner end. Now owner end is used define the relationship. 

Actor -> 
![[Pasted image 20240722170601.png]]

Movie -> 
![[Pasted image 20240722170546.png]]


Demo ( )
![[Pasted image 20240722171552.png]]

How to add actors to existing movies.

![[Pasted image 20240722173223.png]]

Explain this case -> 

![[Pasted image 20240722174836.png]]

Explain about what is the reason tharindu cannot remove name from asai bayai movie from him self. (only owner can do that)

==Q: ==What is the reason that Tharindu cannot remove movie 'asai bayai ' from his name:
==A:== Only Owner Can Remove It. In here  Movie is the owner.

==Q: ==What happen if tharindu added a movie on his name
==A:== This added because when persistence bag is dirty  save and update is happen

==When there are attributes in the associate table==

[[How to connect the app with mysql through docker]]

![[Pasted image 20240723075329.png]]

![[Pasted image 20240723075347.png]]



![[Pasted image 20240722194406.png]]

How create the Primary Key in ORM

There are two ways to this. Which method is followed , it is necessary to create  a PK class.

Q.Is pk class a entity class 
A. No. This is not a entity class

Order class -> 



Item Class -> 



PK Class -> 

![[Pasted image 20240723113050.png]]
`order` and the `item` should have the same name as the order detail class.
`@Column` annotations are not mentioned
orderDetial class -> 

![[Pasted image 20240723104616.png]]

Totally participation of the order should be handled through the application.

![[Pasted image 20240723104636.png]]

demo -> ()

![[Pasted image 20240723111311.png]]


Order is set to bidirectional and constructor, to stirng, setter methods issues should be fixed 

![[Pasted image 20240723112104.png]]

explain how does the all arg constructor works -> 

==How to handle there is no any order details in the order detail list. ==

-Now exception is thrown when there is no item in the order details list. 

![[Pasted image 20240723114106.png]]

How to retrieve the order detail

![[Pasted image 20240723124603.png]]

order details pk is used for to retrieve the order detail.Other wise there is no way to use the id of the order detail.