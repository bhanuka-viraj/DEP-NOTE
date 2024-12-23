
|                                              |                                                                                                                                                                                                                                                                                    |
| -------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Angular content project <br>means in angular | ![[Pasted image 20240731145129.png]]<br><br>insert, or "project," content from a parent component into the <br>template of a child component. This enables the creation of highly reusable and flexible components that can display <br>custom content provided by the parent.<br> |
| What is the default status                   |                                                                                                                                                                                                                                                                                    |
| How to project content in child              | ![[Pasted image 20240731145519.png]]<br><br>using `<ng-content/>`  component it can  be displayed. It  only project only once even if `<ng-contene>` is used several times                                                                                                         |
| How to use content seperately                | ![[Pasted image 20240731145904.png]]<br><br>selector should be eplicityl defined in the `ng content`                                                                                                                                                                               |
Explain this -> 

Display -> ![[Pasted image 20240731150220.png]]

Child -> 
![[Pasted image 20240731150317.png]]


AppComponent (parent)-> 
![[Pasted image 20240731150304.png]]



==Q.== How to get input element separately -> 
==A== Define the type of the input explicitly 

![[Pasted image 20240731150602.png]]

![[Pasted image 20240731150615.png]]

![[Pasted image 20240731150659.png]]

Q. How to use CSS selectors like class and id
A. refer the `.dep` and  `div-1`
parent -> 
![[Pasted image 20240731151056.png]]

child -> 
![[Pasted image 20240731151118.png]]



|                                                                       |                       |
| --------------------------------------------------------------------- | --------------------- |
| What is the directive <br>that is used for the <br>content projection | `ngProjectAs`<br><br> |
==Q.== How to use `ngProjectAs` directive

parent -> 
![[Pasted image 20240731151856.png]]

child -> 
![[Pasted image 20240731152011.png]]

![[Pasted image 20240731152030.png]]

Note -> There are two type of `ng-content` -> 
1.Single-slot 
2.Multi-slot 

Single slot means using only one slot. All components comes to this slot.
Multi slot means using multiple `ng-content` with a selector. This allow to filter the component through css selectors