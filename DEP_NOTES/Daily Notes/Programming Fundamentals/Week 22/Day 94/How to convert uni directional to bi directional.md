git link -> https://github.com/IJSE-Direct-Entry-Program-12/jakarta-ee/tree/main/jpa/04-relationships/one-to-one/src/main/java/lk/ijse/dep12/jpa/relationship

Set the `@OneToOne(mappedBy)` in the inverse end
![[Pasted image 20240715164552.png]]

A error is occurred due to not found the right constructor

Now spouse has been added to the all args constructor to the employee. But employee does not need a spouse to create a employee. Then create a constructor in employee without the spouse 

![[Pasted image 20240715164922.png]]
 
Stil get a error. This is a stack overflow error. Because to string of the employee and spouse are executed recursively. add `@toString` annotation and exclude the  string of the owner end at the inverse end

![[Pasted image 20240715165403.png]]

What are the changes that need be done when set the uni directional to the bidirectional

->Change the constructor
->exclude the toString of the owner side in the inverse side
->need to be addressed the seter method in inverse side. In this case setSpouse( ) method

|                                                                                                                         |                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| What is the difference <br>between owner end and<br>inverse end (in terms <br>of how they care to the <br>relationship) | Owner ends cares the relationship and inverse end <br>does not cares the relationship<br><br>add the git link in here |
| can it be fix the setter <br>method in bidrectional                                                                     | Some time this is not possible to fix 100%.                                                                           |

==NOTE -> Only use bidirectional if it is required ==

How to fix the Constructor(case when a employee is created with the already associated spouse)

![[Pasted image 20240715172105.png]]
remove the `@allArgsConstructor` annotation and create the all args constructor with the following changes 

![[Pasted image 20240715172216.png]]

Now this not allowed to create a new employee with the already associated spouse with a another employee


==How to fix the setter method==

Best way is the remove the setter method -> 
set the setter access level none
![[Pasted image 20240715172734.png]]

Also can be changed the setter method of the inverse end that similar to works in the owner end

![[Pasted image 20240715173007.png]]

