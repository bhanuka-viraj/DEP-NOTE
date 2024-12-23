nod libraray -> https://www.npmjs.com/package/mongodb

complete note -> 

==How to create the connectivity== -> 

![[Pasted image 20240813144827.png]]

==How to insert a data== ->
![[Pasted image 20240813144912.png]]


==How to to insert multiple data in same time== (no method statement in mongo db) =>
![[Pasted image 20240813145003.png]]

There is a type alias called Customer 

![[Pasted image 20240813145038.png]]

How to delete multiple records in once 
How to update records


==How to select records (retrieve)==
![[Pasted image 20240813144519.png]]

simplify version -> using `for await`
![[Pasted image 20240813144640.png]]


==What are the API that could find with the mondoDB== =>
How to use those api

|                                                          |                                                                                                                                                       |
| -------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| <br>`insetOne(doc)`<br>`insertMany([doc,doc,..])`        | `insertOne(doc)` -> <br>to create a one doc<br><br>`insertMany([doc,doc,])`-><br>to insert multiple documents in once, a document array should be pas |
| `updateONe(predicate,doc)`<br>`updateMany(preicate,doc)` | `updateOne()` -> filter should be as the predicate                                                                                                    |
| `deleteOne(predicate)`<br>`deleteMany(predicate)`        |                                                                                                                                                       |

