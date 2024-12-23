

==When only one side is with fully participation==

![[Pasted image 20240716021540.png]]
![[Pasted image 20240716021555.png]]
1.Take the id of the partial participation side to the total participation side as the foreign key. Then set the constraints to the foreign key `NOTNULL and UNIQUE`. If there any attributes in the relationship , they goes to the foreign key side.
(ex for attributes in the relationship -> which used add the employee spouse relationship and when)


==When both sides are with fully participation==

![[Pasted image 20240716021830.png]]
![[Pasted image 20240716021844.png]]

[[Example for both side fully participation]]

One side can be chosen as the owner end. (as we wished).Take the id of the inverse end to the owner end as the foreign key (wIth `UNIQUE and NOTNULL` constraint) and also  attributes of the relationship goes to the foreign key side. Only Owner end is work as the fully participation in the database level. The inverse end should be handle by the application (business logic) to work as the fully participation. 

![[Pasted image 20240717104253.png]]

When there are more than one relationship between these entities , associate table is created instead adding the attribute of relationship to the owner end. 

==When the both side with partial participation==

There are two method for this case -> 

Method 1 ->(Only `UNIQUE` is used as the constraints key)
![[Pasted image 20240716024105.png]]

![[Pasted image 20240716024239.png]]

One side can be chosen as the owner end. (as we wished).Take the id of the inverse end to the owner end as the foreign key (wIth `UNIQUE` key constraint) and also add attributes of the relationship goes to the foreign key side. Null values can be stored in the owner end. 

==Note== -> Null values decrease the performance of the database. When select the owner end it should be select with minimum possible null values. In this case if employee is selected as the owner end then there are lot of null values than the choosing  vehicle as the owner end. 


Method 2 -> (using associate entity)
 
![[Pasted image 20240716024651.png]]
![[Pasted image 20240716024737.png]]

One side can be selected as the owner end. Then take the id of the owner end as a primary key to relationship as and  take the id of the inverse end to the relationship as the foreign key with `NOTNULL` and `UNIQUE` key constraints. Now this relationship is called as the associated entity.  Also any other attributes in relationship can be added to this associate table.
