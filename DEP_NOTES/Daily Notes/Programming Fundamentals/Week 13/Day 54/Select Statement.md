

|                                                                  |                                                                                                                                                                                                   |
| ---------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What are the two <br>orders in SQL<br>statements                 | Lexical Order<br>Logical Order                                                                                                                                                                    |
| What is lexical Order<br>of delete statement                     | <br>ex-><br>`DELETE FROM <tblName> WHERE <search>`<br>lexical order -> DELETE FROM WHERE<br>(variable should not be included)                                                                     |
| What isl logical order                                           | Logical statement is not represent the execution order in<br>the data base . It is used to understand the execution<br> order of query for developers                                             |
| What is the logical<br>order and the lexical<br>order of DELETE  | ![[Pasted image 20240507191202.png]]                                                                                                                                                              |
| What is the logical <br>order and the lexical<br>order of UPDATE | `UPDATE <tblName> SET col=val, WHERE <serach condtion>`<br><br>lexical -> UPDATE SET WHERE<br>logical -><br>WHERE `<search condtion>`<br>UPDATE<br>SET column = value                             |
| what is the logical <br>and lexical order of<br>INSERT           | `INSERT INTO <tblName> (id,name) VALUES (1,'Kasun)(2,'Nuwan')'`<br><br>lexical -> INSERT INTO VALUES<br>logical -><br>VALUES (1,'Kausn'), (2, 'Nuwan')<br>INSERT INTO `<tblName>`<br>[(id, name)] |
What is the syntax of Select statement 
![[Pasted image 20240507194502.png]]
what is the lexical order of SELECT statement

![[Pasted image 20240508105408.png]]

 SELECT -> DISTINCT | ALL -> FROM -> WHERE -> GROUP BY -> HAVING -> ORDER BY -> ASC | DESC -> OFFSET -> ROW | ROWS -> FETCH -> FIRST -> ROW | ROWS -> ONLY 

(parts from 9 to 14 can be changed with the dbms)

|                                                         |                                                                                                             |
| ------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| What is the difference<br>between `ALL` and `DISTINCT`  | `ALL` add all values including duplicate values. <br>`DISTINCT`  does not included the duplicate <br>values |
| ==what is the purpose of using <br>`SELECT` statement== | to crate e derived / virtual table                                                                          |
try this 
![[Pasted image 20240507201636.png]]

|                                                      |                                                       |
| ---------------------------------------------------- | ----------------------------------------------------- |
| What does happen with<br>the `*` in SELECT statemetn | it is a `<Selectlist>`<br>it represent the all column |

==What is the logical order of the select statement and explain one by one==

![[Pasted image 20240508105333.png]]

1 `FROM <table(s)>`
Take the data from the table or comma separated tables,

2.`WHERE <searhc condition>`
Set a searching condition to the data that take from the source tables

3.`GROUP BY <col, col, col> 
Group the data that taken from the table

4.`HAVING<search condtion>` 
Apply search condition for grouped data

5.`SELECT` 
 SELECT the table that has been created virtually so far

6 . `DISTINCT | ALL` 
set decide whether get the ALL or DISTINCT

7 `<select list>` 
add comma seperated select list (*, column name)

8.`ORDER BY col[ASC][DEC], col[ASC][DEC]`
The column can be order in the virtual table

9.`OFFSET <Offset row count>`
skip the first lines of the  virtual table

10.`FETCH {FIRST | NEXT} <row count> {ROW | ROWS} ONLY
 Fetch the rows from virtual table

|                                                                                                                                     |                                                                                                                                                                                                                                                              |
| ----------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ==What is the reason to <br>have two difference serach<br>condtions in `WHERE<Search condition>`<br>and `HAVING<search condtion>`== | `WHERE<Search condition>` is used to applied a <br>search condition when data get from the source <br>(to filter from the data source)<br><br>`HAVING<search condtion>` is used to applied a search condition after group<br>(to filter after the group)<br> |
|                                                                                                                                     |                                                                                                                                                                                                                                                              |
describe this ->
`SELECT id emp_id, name emp_name FROM employee ORDER BY emp_id DESC`

get the data from the employee table and get the all values of the table. Get the id and name column from virtual table and change their name respectively emp_id and emp_name. Order the virtual table values according to the descending order of the emp_id vlaues.


