
what happen when merge ->

case 1 -> 

![[Pasted image 20240711152053.png]]

output -> 

![[Pasted image 20240711152135.png]]

Explanation ->

When execute the `merge()` first check is there a entity in the persist context same as the entity that need to be merged. if there is no entity to the same id, then create a new entity(proxy).Then get the records to  this newly created entity from the data base executing a select query.Now merge two entities. When merge it identify name of the entity has been changed and it set the new name to it. Now dirty flag is set true.When check the dirty flag update is done.Returns the newly created entity

Case 2 -> 

![[Pasted image 20240713225825.png]]

![[Pasted image 20240713225548.png]]

Explanation -> 
When execute the `merge( )` first check is there a entity in the context that is similar to the dispatched entity. In this case there is a entity in the context matches with the dispatched entity. Now entities are merged. When merge it is found that the name of the entity has been changed and then set the new name to entity that was in the context and return it. 

Case 3 -> 

![[Pasted image 20240711171318.png]]

Explain this  -> 

First create a new entity that is in the transient state. Database already has record for this id. When merge is executed first check is there a entity in the context  similar to the entity  in the transient state. There is no entity in the context. Then create a new entity(proxy) and get the details from the database record. Now it is found the name has been changed and new name set the new created entity.Dirt flag is set the true and update is done during the commit.

Using this update can be done.

Case 4 -> 

![[Pasted image 20240711172738.png]]

![[Pasted image 20240711172826.png]]
Explain this

New entity is created in the transient state. When execute the merge new entity is created in the context and this time there is no record in the database that match with the transient state entity.This is time dirty flag is not changed. Now schedule a `INSERT INTO`.