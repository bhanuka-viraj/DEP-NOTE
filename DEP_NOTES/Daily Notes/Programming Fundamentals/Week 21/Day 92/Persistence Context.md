![[Pasted image 20240712084559.png]]


1.Transient (new) State -> 
If there is no record in the database that matched it is called the transient state. Hibernate will know about this when it check the id in the data base.

2.Manage State ->
When a entity is in the persistence context, It is called Manage state

3.Detached State ->
When there is a record in the data base to the that match to the primary key and the element is not in the persistence context it is called that element  is in the detached state

4.Removed state ->
entities that were in the persistence context but now they are not in the persistence context. Now they are not in the managed state. But they can go to the manage state again and the persistence context still refer those entities. 

|                       |                                                                                                                                                                                                                                                                                                                                 |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| when `remvoe()`       | managed state to removed state                                                                                                                                                                                                                                                                                                  |
| when `persist()`      | Transient  state to managed state<br>Removed state to managed state<br><br>Schedule a  `INSERT INTO`                                                                                                                                                                                                                            |
| when `detach()`       | managed state to detached state                                                                                                                                                                                                                                                                                                 |
| when `merge():entity` | detached state to managed state<br>transient state to managed state<br><br>this return entity                                                                                                                                                                                                                                   |
| when `refrech()`      | manged state entity are synced with the table row<br>(this is only can be applied to the manged state elements in JPA)<br><br>In JPA, the `refresh()` method is used to synchronize the state of a managed entity with the current state of the database<br><br>In native hibernate this can be done to the detached state too. |
| when <br>`clear()`    | All entities in the managed sate are send to the detached state<br><br>Clear the all Scheduled transaction in the server side transaction context                                                                                                                                                                               |
| `commit()`            | sync with the data base. This is also can be done using the <br>`flush()` before the transaction                                                                                                                                                                                                                                |
| `contains()`          | to check whether a entity is contain in the pesistance context                                                                                                                                                                                                                                                                  |

|                                                        |                                                                     |
| ------------------------------------------------------ | ------------------------------------------------------------------- |
| What is the first <br>level cashe<br>(presist context) | Entities are associated in the entity manager                       |
| what is the purpose of using<br>first level cashe      | To ehance the performances                                          |
| What is the second level<br>cashe                      | Enitities are associated with the entity manager factory<br>context |

`find() /getRefernce( )` ->

![[Pasted image 20240711142510.png]]
this is only get the entity from the database only once. When entity comes to the managed state not required to get the record from the table again and again.Just return entity that in the persistence context

[[How does the detach works]]

[[How does the remove( ) works]]

[[How does the merge( ) works]]

|                                                                 |                                                                                                                                       |
| --------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| can it be use `merge()`<br>to update                            | update can be done using the `merge()` for detached <br>elements. <br><br>refer the third case in the [[How does the merge( ) works]] |
| How does the spring <br>do save                                 | spring use merge to save                                                                                                              |
| What is the difference<br>between `detach()` <br>and `clear( )` | Clear send the all entity to the detached state and <br>clear all schedules                                                           |

[[Flush vs Commit vs Rollback]]
[[How does the refresh works]]

|                                      |                                                                                                                                                  |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| update( ) statement<br>in native<br> | update take the detached state<br>element to the managed state as it is (in merger same<br>element does not come). `update()` schedule a update. |
| SaveOrUpdate( )<br>in native         | if the entity is in the transient state it is saved , if the <br>entity is in the detached state then it is updated.                             |
