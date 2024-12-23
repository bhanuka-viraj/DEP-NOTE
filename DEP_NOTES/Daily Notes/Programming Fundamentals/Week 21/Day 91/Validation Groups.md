
|                                                      |                                                                                                                                                                                                                                                                                                       |
| ---------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the reason<br>to use groups In<br>validation | Validation groups in Java's Bean Validation framework are used to categorize and control the validation constraints that should <br>be applied during different phases or contexts of an application's lifecycle.<br><br><br>By default all constraints are run called `Default` validation <br>group |
|                                                      | Validation group is a marker interface                                                                                                                                                                                                                                                                |

Step 1 -> 
Create a interface called update

Step 2 ->
add the group to the necessary annotation 
![[Pasted image 20240710120135.png]]

step 3 -> 
add the Update interface to the validation l
![[Pasted image 20240710120550.png]]

step 4  -> 
Now default group validation are not worked. Then update interface is extend from the interface called `Default`

![[Pasted image 20240710120252.png]]
