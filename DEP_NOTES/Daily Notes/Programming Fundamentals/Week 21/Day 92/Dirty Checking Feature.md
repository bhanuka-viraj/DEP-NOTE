![[Pasted image 20240712084559.png]]
[[Persistence Context]]

There are four state of the entities

1.Transient (new) State
2.Managed State
3.Detached State
4.Remove State

Managed state elements are in the Entity Manager context (this is also called as the 1st level cache). Manged State elements come to the entity manager context from data base using the api `find( )` and `getReference()`. There is a flag in this elements called `ditry`. Dirty flag is only applicable for the entities in the managed state. When some changes happen to the element the flag is turn in to true. Default this is in false. When commit the transaction dirties flags are checked do the execution for it.. Even if some entity is changed using setter , but there is no difference between the previous value then dirty is not gonna changed to true. This is called the dirty checking feature


![[Pasted image 20240712084053.png]]