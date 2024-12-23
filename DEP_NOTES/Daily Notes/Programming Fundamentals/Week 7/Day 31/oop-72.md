add gitHub link -> https://github.com/IJSE-Direct-Entry-Program-12/object-oriented-programming/tree/main/oop-72

![[Pasted image 20240313144457.png]]

![[Pasted image 20240313143415.png]]


The order of the interfaces is not concerned. But if there is a extend between the interface the order of the extended  interfaces is  concerned. In this case both interface 3 and interface 2 has been implemented within the MyClass. Interface1 has been extended with the extended interface 2. It is clear when see the diagram there are two my method in the interface area. when they are extended first check the myInterface 2 and if it not found in there then check interface1.This not heading to a diamond case. But if interface3 has the same method as the myinterface 2 and 3. There diamond problem is occurred. 