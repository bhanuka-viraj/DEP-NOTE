Employee - Spouse

git link -> https://github.com/IJSE-Direct-Entry-Program-12/jakarta-ee/tree/main/jpa/04-relationships/one-to-one/src/main/java/lk/ijse/dep12/jpa/relationship

==conceptual ->==

![[Pasted image 20240716015811.png]]

==Logically and Physically -> ==

->First develop the table with the dependency
->Foreign key constrain should be added. It enhance the indexing. Then enhance the performance.

![[Pasted image 20240715141919.png]]
Explain -> 
1.Starts with the zero dependency entity. In this case employee does not have any dependency 

2.Next create the less dependency entity.

2.ADD the foreign key constraints. 

|                                      |                                                                                       |
| ------------------------------------ | ------------------------------------------------------------------------------------- |
| What is owner end<br>in relationship | The end that is created the realationship<br><br>In This case spouse is the owner end |
| What is Inverse end                  | The opposite end of the owner end. <br><br>In this case employee is the inverse end   |


![[Pasted image 20240715143913.png]]
This is the Inverse end

![[Pasted image 20240715143937.png]]
This is the owner end

|                                                |                                                                                                                                                                                                |
| ---------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the Uni Directional<br>relationship    | Relationship where only one of the participating entities is aware of the relationship. This means that only one entity contains a reference to the other entity, and the reverse is not true. |
| What is the bi<br>directional <br>relationship | relationship where both entities involved in the relationship are aware of each other. Each entity contains a reference to the other, allowing navigation and operations in both directions.   |
[[How to convert uni directional to bi directional ]]

[[Mapping Rules for One to One]]





