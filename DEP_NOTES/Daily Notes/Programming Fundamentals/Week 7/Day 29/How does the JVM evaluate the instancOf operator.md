
gitHub link -> https://github.com/IJSE-Direct-Entry-Program-12/object-oriented-programming/blob/main/oop-55/src/AppInitializer.java

![[Pasted image 20240311165315.png]]

![[Pasted image 20240311164716.png]]

in here checking the  " dog instanceOF Dog" =>
dog typed variable that is referred a dog object is compared with a Dog blue print.

First find the instance using the memory location. Then identify the secret link between instance and the class object. Then find out the whether comparing blue print (blue print operand in the instanceOf operator) could be find within the class object  chain that is secretly link to the object. 

Dog's class object  can be found in the  secretly linked class object chain of the instance Dog.
Animals's class object  can be found in the  secretly linked class object chain of the instance Dog.
Objects class object  can be found in the  secretly linked class object chain of the instance Dog.

![[Pasted image 20240311165434.png]]


now checking the  " a instanceOF Dog" =>

Animal type a variable that is referred to cat object is compared with a Dog blue print. It cannot be found the Dog's blue print within the cat's class object chain. Then this return a false. 




