Also the `remove()` schedule a delete.

Explain this case ->
![[Pasted image 20240711150341.png]]

![[Pasted image 20240711150415.png]]


In here first two scheduled has been ignored. Only last insert is scheduled. This is how it happens in the JPA but in the Native languages all three are scheduled.  