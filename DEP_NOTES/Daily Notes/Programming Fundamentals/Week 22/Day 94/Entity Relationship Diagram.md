
|                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| What is chen-like<br>ERD          | This was introduced by the Chen                                                                                                                                                                                                                                                                                                                                                                                                                  |
| What is ERD <br>stand for         | Entity Relationship Diagram                                                                                                                                                                                                                                                                                                                                                                                                                      |
| What is ERD                       | ->An **Entity-Relationship Diagram (ERD)** is a visual representation of the entities within a system and the relationships between those entities. It is used in database design to illustrate the logical structure of databases, showing entities, their attributes, and the <br>cardinality and participation constraints of the relationships.<br><br>-> ERD no need be 100% correct<br><br>->This show how does entity / record looks like |
| Does ERD only works<br>with RDBMS | No. This can be used with NOSQL too                                                                                                                                                                                                                                                                                                                                                                                                              |
Note -> ERD is used as Sketch. Not used as a blueprint or prototype


![[Pasted image 20240715133416.png]]
![[Pasted image 20240715134933.png]]

`1` => One (cardinaty)
`M` => Many (cardinaty)
`double-line` => Fully Participation (participation)

How to determine the relationship ->

In this customer and order relationship customer and order side has `1-M` relationship, Order and customer side has a `1-1` relationship. So the relationship between customer and order is ONE-MANY
`1-M + 1-1` -> 1 - M
`1-1 + 1-1` -> 1 - 1
`1-M + 1-M` -> M-M

UML notation ->

![[Pasted image 20240715135157.png]]

`0..1` -> 1 or Zero
`1..1` -> only one
`1..*` -> One or more than one
`0..*`  -> Zero or many
``



