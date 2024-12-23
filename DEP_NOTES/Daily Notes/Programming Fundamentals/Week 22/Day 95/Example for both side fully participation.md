
add the git link here ->


![[Pasted image 20240716124749.png]]

How to define the data and time in entity (In ORM)
![[Pasted image 20240716124530.png]]

Customer -> 
`add cusotmer class here`

Account ->
`add account class here`

How to handle the fully participation of the Customer (inverse-end) in the app ->

==Method 1->==
Both account and the customer should be persist inside the one transaction -> 


![[Pasted image 20240716131406.png]]


Method 2 -> 

==When the relationship is bidirectional==

Account is created using the all args constructor of the customer.

![[Pasted image 20240716132224.png]]

Now the following changed should be done to the customer class -> 

change  the all args constructor
 ![[Pasted image 20240716132502.png]]
 
 add the cascade to the customer to persist the account when persist the customer
 ![[Pasted image 20240716132707.png]]


==When the connection is unidirectional==

add the cascade to the account to persist the customer when persist account

![[Pasted image 20240716133204.png]]

![[Pasted image 20240716133026.png]]

