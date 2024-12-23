![[Pasted image 20240313133045.png]]

![[Pasted image 20240313133101.png]]

There is a unimplemented method calledc myMethod( ) in MyInterface. There is no method to override the myMethod( ) in both sub class and super class. Now check the super class of the child class to override the method in interface. 

![[Pasted image 20240313133127.png]]

What is the reason for the error =>
 Now there is a method in  Child class to override the  (super class of the interface) method myMethod( ). But it is a abstract method. So it need to  be overridden. This is the reason for the error.
