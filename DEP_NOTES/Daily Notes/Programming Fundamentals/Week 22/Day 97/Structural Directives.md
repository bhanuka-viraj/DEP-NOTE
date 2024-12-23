Structural directives are used to take the control flow statement to the html. There are in built directives in angular. `ngIf`, `ngFor`, `ngSwitch`. Also we can create Structural directives. But usually do not do that. 

|                                                |                                                                                                                                                    |
| ---------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| What are the build<br>in structural directives | -> NgIf<br>-> NgFor<br>-> NgSwitch                                                                                                                 |
| What is the <br>micro-syntax                   | The way this directives are defined in the HTML<br><br>`*` is used for this<br><br>`*ngIf`<br>`*ngFor`<br><br>![[Pasted image 20240718131150.png]] |
### ngIf

syntax -> 


![[Pasted image 20240719075233.png]]

how does this works -> 
when the  value of the boolean expression is changed particular element can be displayed or hidden base on the boolean value

how to use built in directives in standalone module

should be imported the `CommonModule` in component.ts. Because common module contains those directives
![[Pasted image 20240718132614.png]]

This is how `*ngIF` is used. `<p>` is display and hide base on the boolean value
![[Pasted image 20240718132652.png]] 

How to use the public members of the controller (ts file) as the boolean expression.
![[Pasted image 20240718133219.png]]

![[Pasted image 20240718133336.png]]

When click the button  public variable `flag` in the controller is set to it's complement. paragraph is display or hidden base on the boolean value

==How to use else with the ngIf==

![[Pasted image 20240718134011.png]]

![[Pasted image 20240718134045.png]]

Using [[ng templates]]


This is the new syntax =>

![[Pasted image 20240718135828.png]]

![[Pasted image 20240718135727.png]]

### ngFor

How does the ngFor work -> 
In Angular, the `ngFor` directive is used to iterate over a collection (like an array) and render a template for each item in the collection. It is an essential tool for dynamically displaying lists of items.

old syntax ->

![[Pasted image 20240718142327.png]]
![[Pasted image 20240719082819.png]]
![[Pasted image 20240718142304.png]]

[[local variables in ngFor]] -> `index`, `fist` ,`last`, `even`, `odd`

using local variables =>
![[Pasted image 20240718143019.png]]

there are two ways to use set the identifier for this attributes

![[Pasted image 20240718143330.png]]

![[Pasted image 20240718183715.png]]

[[TrackBy Function]] -> refer this for the track by function definition

|                                                            |                                                                 |
| ---------------------------------------------------------- | --------------------------------------------------------------- |
| what happen when<br>the track by is not<br>added to ng-for | ng-for track array items, via array values                      |
| what happen when <br>the track by is added                 | now it allowed us to change the track by value as we neccessary |

explain this using what happen when arrays wit the object. how does it check the reference , how does it added the new item checking the values.

[[Data binding in Angular]]

How does the track by function is worked when there is a data binding for other properties that is not used for the track by function

New Syntax =>

![[Pasted image 20240719083544.png]]

`@empty` is worked when there is no items to display
### ngSwitch

old syntax -> 

![[Pasted image 20240718190653.png]]

![[Pasted image 20240718190730.png]]

also ng-container can be used as a alternative to the div
(when there is no hosting element)

![[Pasted image 20240718190853.png]]

New Syntax ->

![[Pasted image 20240718191311.png]]