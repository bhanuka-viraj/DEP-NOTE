
|                                                                |                                                                                                                   |
| -------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| What is the purpose<br> of using attribute <br>directives      | Attribute directives in Angular are used to change the <br>appearance or behavior of DOM elements and components. |
| Where attributes <br>directives are used                       |                                                                                                                   |
| what are the built in<br>attributes directives                 | Mainly there are two attributes directives<br>=> NgClass<br>=> NgStyles                                           |
| What is the module<br>that is included the<br>above attributes | common module                                                                                                     |


### NgClass - Class Attribute Directive

|                                          |                                    |
| ---------------------------------------- | ---------------------------------- |
| What is the purpose <br>of using NgClass | To add the CSS classes to elements |
syntax -> 


![[Pasted image 20240719112032.png]]

What are the things that can be used as the expression -> 
1.String
2.A object (key ->    value -> boolean)
3.String Array

example -> 

![[Pasted image 20240719111934.png]]

![[Pasted image 20240719111949.png]]

also allow to use `[class]` instead `[ngClass]` -> 

![[Pasted image 20240719112124.png]]


With this code now button add and remove the classes dynamically using the string class 
![[Pasted image 20240719112437.png]]

also classes can be set through a array 

![[Pasted image 20240719112832.png]]

How to use object with ngClass

If the object is changed directly rather changing properties of the object from outside. We can see the changes. But it is done using the flag rather changing object directly this won't work.

![[Pasted image 20240719114010.png]]


In any case if it require to make changes  rather using properties of the object  directly. These method need to be used -> 

![[Pasted image 20240719115006.png]]

![[Pasted image 20240719115021.png]]

there is a simple way to do this when it is only need to set a single class 

![[Pasted image 20240719120217.png]]


![[Pasted image 20240719120031.png]]

![[Pasted image 20240719120115.png]]

![[Pasted image 20240719120130.png]]

`[class]` has been used to bind the single classes since the angular 2. Since angular 18 now it is allowed to use `[class]` with multiple classes  instead using `[ngClass]`

### NgStyle - Style Attribute Directive

![[Pasted image 20240719121140.png]]

What are the things that can be used as the expression



How does this works with string -> 

![[Pasted image 20240719121913.png]]

`[ngStyles]` only works with the object

Like in the `ngClass` to change the style with the external state a method should be called and the it should be invoked when the flag is changed. 

![[Pasted image 20240719122845.png]]
![[Pasted image 20240719122857.png]]

How to do this only using single style ->

If only require to change a single style this syntax can be used.

add syntax here

![[Pasted image 20240719123700.png]]


![[Pasted image 20240719123727.png]]

### Attribute Attribute Directive

This is also a built in directives and called also  ng Attribute Directive

What is the purpose of using this -> to works with attributes of the elements. 


![[Pasted image 20240719125650.png]]![[Pasted image 20240719125719.png]]


### NgNonBindable

What does this do -> Disable the all data binding. This does not impact only for the particular element. Also impact for child elements too.
![[Pasted image 20240719130920.png]]
this impact for the parent and all child elements
