
|                                            |                                                |
| ------------------------------------------ | ---------------------------------------------- |
| What is the data flow <br>of event binding | data are being flow from display to controller |
|                                            |                                                |

#### Event binding with HTML element => 

Works as the event listeners and data are passed from the template to controller

html => 
![[Pasted image 20240725180136.png]]

now flag is changed when the button is clicked


![[Pasted image 20240725181527.png]]\


using `envet binding` and `text interpolation` together

html => 
![[Pasted image 20240725182129.png]]

ts => 
![[Pasted image 20240725182151.png]]

![[Pasted image 20240725182204.png]]

How to get the event data to the ts file. => 

HTML => 
![[Pasted image 20240725182801.png]]

Ts file => 

![[Pasted image 20240725182837.png]]

####  Event Binding with Angular component => 

When a property is decorated with `output` this is act as property binding. ==This is used to transfer data from child component to parent component.==  The data type of the this should be `EventEmitter.` 

`template statement` should be passed to the event binding. Also multiple `template statement` can be used. Usually method invocation statement, simple assignment statement are used.

##### child component  => 

ts file ->
![[Pasted image 20240725185358.png]]
html file => ![[Pasted image 20240725185457.png]]

##### Parent Element => 
html file => 

![[Pasted image 20240725185547.png]]


ts file => 
![[Pasted image 20240725185615.png]]

