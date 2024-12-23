
![[Pasted image 20240725173623.png]]


 
|                                                 |                                                             |
| ----------------------------------------------- | ----------------------------------------------------------- |
| What is the data <br>flow of text interpolation | Data is being flow from `controller ` to `Template`<br><br> |
### Property Binding with HTML Element

![[Pasted image 20240725170422.png]]

when flag is true =>

![[Pasted image 20240725170437.png]]

![[Pasted image 20240725170450.png]]

when flag is false => 

![[Pasted image 20240725170527.png]]

![[Pasted image 20240725170538.png]]

 Also functions can be used for the property binding 

![[Pasted image 20240725171511.png]]

![[Pasted image 20240725171523.png]]

![[Pasted image 20240725171544.png]]

what is the difference between attribute binding and property binding

attribute binding is the attributes that provided by the angular. These are not commonly used. Best practice is using property binding as much as possible. 


=> What is the difference between html attribute and angular attribute binding 
![[Pasted image 20240725172239.png]]

![[Pasted image 20240725172309.png]]

![[Pasted image 20240725172326.png]]

angular attributes is allowed to pass ts expression while html attributes only allow string.

### Property Binding With Angular Component

These are used to pass data from parent component to child component

child component => 

html=> 
![[Pasted image 20240725173834.png]]

ts =>

![[Pasted image 20240725173858.png]]
if these inputs are not named as `first` and `second` these variables (work similar to the properties of the `<app-first/>` element) they  are accessed using their names (`firstInput` and the `secondInput`)

parent component => 
 html = >
 ![[Pasted image 20240725173944.png]]

ts => 
![[Pasted image 20240725174006.png]]


![[Pasted image 20240725174018.png]]
