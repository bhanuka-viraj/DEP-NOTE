==Q.== What is the use of FULL OUTER JOINS 
==A.== This is very important when find the symmetric difference

![[Pasted image 20240805140618.png]]

To get the full outer join
![[Pasted image 20240805141008.png]]

to get the UNION of the A-B and the B-A ( this is the symmetric difference)

![[Pasted image 20240805141136.png]]


How to get the FULL OUTER JOIN if dbms does not support for it => 

![[Pasted image 20240805141351.png]]

Use the `UNION` clause to combine those queries as the UNION

![[Pasted image 20240805141915.png]]

How to get the symmetric difference -> 

1.Removing the intersection part from the FULL OUTER
2.A-B ∪ B-A

[[NATURAL INNER JOIN]]
