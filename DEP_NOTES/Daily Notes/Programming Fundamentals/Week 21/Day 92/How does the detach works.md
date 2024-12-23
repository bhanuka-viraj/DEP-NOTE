
`detach()` ->

what is the difference between `detach()` and `remove()` ->
when a element is send to the detached state the persist context not gonna refer it again. Even it doesn't know the derty flag. This is why the update was not happened. 

![[Pasted image 20240711144404.png]]

update are not scheduled but persist are scheduled. 

refer this to clarify the ==scheduling between persist and update==
![[Pasted image 20240711145311.png]]
This code gives a error because when persist insert into is scheduled.S100 was detached before the commit. Now hibernate cannot find the s100 to do the commit. It means persist schedule a inset into and now cannot execute it. This not happened previous case with the update because update does not schedule.
