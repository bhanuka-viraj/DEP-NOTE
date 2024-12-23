
|                                                                      |                                                                                                                                                                                                                                                                                                                                 |
| -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| How does the join<br>querries work                                   | Create the Cartesian product between the relations.                                                                                                                                                                                                                                                                             |
| what is the use of<br>`ON`                                           | Filter the related things from the derived table that came after the `join`                                                                                                                                                                                                                                                     |
| How many clauses can be <br>used to filter in <br>SELECT             | Three clauses<br> ->`WHERE`, `HAVING`, `ON`.<br><br>->Having only can be used after the group by                                                                                                                                                                                                                                |
| Is it necessary to have <br>foreign key<br>constraints to use `JOIN` | No. It is not necessary to have foreign key constraints <br>use `JOIN`<br><br>WHY -> <br>It is not necessary to have a foreign key to constraints to create a  relationship. But it leads to data integrity between the relationship.<br>                                                                                       |
| What are the type of `JOINS`                                         | -> [[INNER JOINS]]<br>-> [[LEFT OUTER JOINS]]<br>-> [[RIGHT OUTER JOINS]]<br>-> [[FULL OUTER JOINS]]<br>-> [[CROSS JOIN]] (This is an another name for the cartesian product, not necceesary to use `ON` clause)<br><br>These are the main standard joins in SQL speicification<br><br>![[Pasted image 20240805121859.png]]<br> |
| What are the COMMA <br>JOINS                                         | This is allowed to create a join without using the `JOIN`<br>keyword<br><br>A derived joins from the main joins                                                                                                                                                                                                                 |
| what are the SELF JOIN                                               | Joining a table with the it self<br><br>A derived joins from the main joins                                                                                                                                                                                                                                                     |
| What are the NATURAL JOINS<br>                                       | automatically combines tables based on columns with the same names and compatible data types, eliminating duplicate columns from the result.                                                                                                                                                                                    |
| What are the EQUI JOINS                                              | combines rows from two or more tables based on a condition that involves equality between specified columns.<br><br>All of joins are EQUI JOINS in most time                                                                                                                                                                    |
| Does postgres <br>allow to use `JOINS` without `ON` clause           | No. Only CROSS is allowed to use without `ON` but in some database managements system it is allowed to use <br>joins without `ON`<br><br>if JOINS are used without `ON` then derived tables is same as the CROSS for all other JOINS                                                                                            |
|                                                                      |                                                                                                                                                                                                                                                                                                                                 |
 Syntax for the JOINs
![[Pasted image 20240805124203.png]]

notes -> 
=> If join type is not specified then INNER is taken as the default
=> Left and Right is defined according to the specified order . In this case A is the Left and the B is the Right
=> It is allowed to have multiple Joins in the same query

How does the `JOIN` works -> 
-> First create the Cartesian product (including both related and unrelated data - this happen after the `join`)
-> Then use `ON` to filter the related data

what is the logical order of the JOINS

1.JOIN -> get the Cartesian product
2.ON -> filter using the join condition (so far this is a inner join)
3.[JOIN TYPE] use the join type (if joint type is inner nothing do. add the left, right or full for others)


Example -> 

![[Pasted image 20240805131200.png]]

![[Pasted image 20240805131339.png]]

[[INNER JOINS]]

[[LEFT OUTER JOINS]]

[[RIGHT OUTER JOINS]]

[[FULL OUTER JOINS]]

[[NATURAL INNER JOIN]]

Q. What is the Select query syntax with the join => 

![[Pasted image 20240805153150.png]]

-> Lexical Order
![[Pasted image 20240806073603.png]]

-> Logical Order
![[Pasted image 20240806073625.png]]

[[Agile]]
[[Team-project-git]]







