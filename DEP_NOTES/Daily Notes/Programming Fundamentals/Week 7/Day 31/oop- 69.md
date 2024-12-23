gitLInk => https://github.com/IJSE-Direct-Entry-Program-12/object-oriented-programming/blob/main/oop-69/src/AppInitializer.java

![[Pasted image 20240313125759.png]]


![[Pasted image 20240313124602.png]]
In here myMethod( ) in interface is override by the method in the SuperClass. Because when there is no method to override the method in interface in the sub class it is override by the method with the same signature in the super class .

![[Pasted image 20240313224529.png]]

if both super and sub class has methods to override in interface ( in above case).First method in the super class overridden the method in the interface then method in the super class is override by the method in the sub class.


Explain the output when there is only default method in interface
![[Pasted image 20240313130643.png]]

There is no method to invoke in the subclass , then go for the interface area.Then myMethod is invoke in the interface

![[Pasted image 20240313131433.png]]

What would happen when the instance subclass is seen form the super class =>

When the object is seen from the super class subclass is now not available. It means interface is not available too. My method is not gonna override. Then myMethod in the super class in executed. 
