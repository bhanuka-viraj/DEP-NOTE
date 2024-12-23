
==Difference between flush and commit== -> 

Flush -> Send the Schedules from the client side transaction to the serer side transaction (this not committed yet. So not added to the database)

Commit -> When commit, Schedules are send to form the client side transaction to the server side transaction and commit to the data base 


==Difference between clear and rollback== -> 

Clear -> When clear, element are detached and the schedules are removed from the server side transaction. 

Rollback -> When rollback, elements are detached, both server side and client side transaction are cleared.

![[Pasted image 20240711183229.png]]

output -> 

![[Pasted image 20240711183320.png]]
Explain this ->


Note -> When rollback or commit, the particular transaction is cannot be used again and need to start a new transaction. 