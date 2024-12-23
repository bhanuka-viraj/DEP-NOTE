


|                                                                   |                                                                                                                                               |
| ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| What is the command<br>to create directive                        | `ng gener                                                                                                                                     |
| What is -> If the validation cannot be done only using `HTML5` <br>validation.<br><br>-> To minimize the boiler plate<br><br>->   ->  ->  br>->   br>->   br>->   br>->   br>->   br>->   br>->   n.  n.  n.  n.  |
First a custom directive should be created 

Now created directive should be implemented with the `Validator` 
(to register the directive as a validator)

![[Pasted image 20240730141559.png]]

`validate()` method is used for the validation now

`provider:[]` should be added
![[Pasted image 20240730144416.png]]

if validate correctly then return the validation object

Now created validator can be used to template as the html validate attributes 

![[Pasted image 20240730145652.png]]

now `customerName` can be used for all `minlength`, `pattern` and `required` in template

