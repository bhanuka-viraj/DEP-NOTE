There are two methods to do this

![[Pasted image 20240723060613.png]]

Method 1 => (without associate entity)
Many Side is selected as the Owner end primary key of the inverse end is taken as the foreign key for the Owner End. If is there any attributes in the relationship they goes to the owner end. Now it can be have null values in the Owner end this time. This may affect the performance of the database. (There is no `NOT NULL` constraint is used here )

Attributes of the relationship should not be not null.


Method 2 => (With associate entity)

Now this is done using a associate table. Many side is selected as the owner end.
Owner end pk is take as the pk of the associate table and the pk of the inverse side is taken as the fk for the associate table wit the `NOTNULL` constraint. 


(assumption , one law suite cannot be handled by the more than one lawyer)

==Example==

Method 1 -> (without creating a associate table)

lawyer class -> 
![[Pasted image 20240722115912.png]]


law suite class -> 

![[Pasted image 20240722115944.png]]

Method 2 -> (creating a associate table)


==When there is no attribute in the relationship==
![[Pasted image 20240723060707.png]]
![[Pasted image 20240722122711.png]]

lawyer -> 
![[Pasted image 20240722123411.png]]

law suite ->
![[Pasted image 20240722123423.png]]

since there is no attributes in the relationship it is not necessary to create another relation for the associate entity. This can be done using the same class of the Lawsuite

changes for the LawSuite should me make like this

![[Pasted image 20240722123853.png]]


Demo class 
![[Pasted image 20240722124812.png]]


records are only added to the associate table when the law_suite is only taken by a lawyer. 

How to deal with the associate table. In here there is no entity class for the associate table. This can be done using the law suite. 

This is how to add a lawyer for a law suite
![[Pasted image 20240722125510.png]]

This is how lawyer change later -> 

![[Pasted image 20240722125908.png]]

How to remove the lawyer from a law_suite -> 
Now the record is removed from the lawyer_lawyer_suite table 

![[Pasted image 20240722130423.png]]


This is work same as the one-one both partially participated cases. 

==When there are attributes in the relationship==

Now it is required to create a entity class for the associate table.

![[Pasted image 20240723060759.png]]
This how LawyerLawSuite class need to be 
![[Pasted image 20240722142147.png]]

In this case there is a own entity class for the associate table. So the adding removing and updating can be done using this entity class. 

Demo class -> 
![[Pasted image 20240722142015.png]]


This should gives a error -> 

![[Pasted image 20240722142412.png]]

Because this law suite ins already assigned to a another lawyer. If it is allowed this relationship should be many to many



