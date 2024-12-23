#### Default Values

In Ts not allowed to create Classes without default values

![[Pasted image 20240724191950.png]]

Otherwise it gives a compile error 
![[Pasted image 20240724192106.png]]


If properties are optional no need to set the default values 
![[Pasted image 20240724192044.png]]

If properties are defined with the not null assertion then  no need to set the default values 

![[Pasted image 20240724192202.png]]



#### Access Modifier
 There are access modiferis that can be used in the ts - > public (default), private ,protected

 private modifier can be used
![[Pasted image 20240724192756.png]]

Protected modifier can be used 
![[Pasted image 20240724193045.png]]


#### Parameters Properties

If the access modifier is defined before the data type in constructor not need create define the class attributes and the constructor body

![[Pasted image 20240724193545.png]]



#### Read Only and Const

![[Pasted image 20240724194105.png]]

When use the `readonly` with attributes of classes not allow to change the value again. Similar feature like final in java 


what is the difference between  `const` and the `readonly` -> 

`const` use to make the final local variables (variables that are created in the stack). `readonly` use to make final the attributes of classes ( variables that are created in the heap) 

Ecma script does not have the `readonly`

![[Pasted image 20240724194300.png]]

But it is not allowed to create leaf classes that similar to java using neither `readonly` or `final`

![[Pasted image 20240724195120.png]]


#### Abstract Classes

Unlike in Js , Ts allow to use Abstract classes. 

![[Pasted image 20240724195237.png]]


####  Enum

Enum can be used in the Ts

![[Pasted image 20240724195621.png]]
![[Pasted image 20240725122453.png]]

Values are automatically increased in enum if values is not defined. 

![[Pasted image 20240725122801.png]]

in enum Gender `FEMALE` is called as the computed value


![[Pasted image 20240725122933.png]]

const can be used with the enum and if const is used it has better performance than the regular enum.   But when there is a computed value within the enum const is not allowed to use. Const only can be used with enum for compile time constant  

#### Inheritance

![[Pasted image 20240725121216.png]]

A class can be only extended by only one clas but can be implemented by the multiple classes (Same as java)
#### Interfaces
![[Pasted image 20240724195944.png]]

Interfaces can be used in the Ts. Methods of interfaces are implicitly public and  and abstract. But it cannot be defined in  method. 

 What is the reason to use interface in Ts =>
=> To define the shape
=> As a abstraction.

Previously interface was used for type aliases. Now interface are used for abstraction. Because now there is specific way to define the type alliance. 

Interface for type aliases => 

![[Pasted image 20240725123926.png]]

Interfaces for abstraction => 

![[Pasted image 20240725124416.png]]

Notes-> 
-> Variables cannot be initialized. But can be declared  in the interface and initialized in the implementation. 
#### LSP Rule

![[Pasted image 20240725124852.png]]

Since type cannot be define in the Js LSP rule cannot be used. But in the Ts LSP rule can be used

Static method cannot be used 

![[Pasted image 20240725124935.png]]
Interface can be extended by the multiple interfaces. 
#### 