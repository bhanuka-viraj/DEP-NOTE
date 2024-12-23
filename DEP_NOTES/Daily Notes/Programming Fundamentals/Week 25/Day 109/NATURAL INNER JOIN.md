![[Pasted image 20240805144725.png]]

Refer the output for this query -> 
![[Pasted image 20240805144748.png]]

![[Pasted image 20240805144833.png]]

Refer the output for this query -> 
![[Pasted image 20240805144906.png]]


Q. What is the difference above case ->
A. When use the JOIN QUERY employee_id has created in the two separated column.  When use the NATURAL INNER JOIN it merges the duplicate column into one.

Q. How to use the USING clause 
In INNER JOINS both side of the equality sign refer the same column, then USING  can  be used for it.

![[Pasted image 20240805145500.png]]
Q. Is `ON` clause allowed to use in the natural. 
A.In Standard SQL reference it is not allowed to used the `ON` Clause

![[Pasted image 20240805150807.png]]

Example - Interview Questions 
==Q.==What is the reason to output nothing in the `NATURAL INNER JOIN`( in name column)
==A.== There are two attributes with the same name but their values are not equal. This is the reason why it gives nothing as the output.

But if is there a at least one matching values in the two attribute with their respective values then it merges in the `NATURAL JOIN`. There is no any Constraints are concerned during the NATURAL JOIN (Foreign Key)


