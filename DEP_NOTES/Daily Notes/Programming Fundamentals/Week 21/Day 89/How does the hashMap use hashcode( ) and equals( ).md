hashMap first invoke the hash code. If there is no object with the same hashcode then not go for the equals( ) method. If there is equal hashcode among objects then go to check the `equals()` method ->

Code that use HashMap -> 
![[Pasted image 20240708145113.png]]

Student class ->

Case 1 ->

Return the unique value for the hashcode

![[Pasted image 20240708145220.png]]


output from the `hashMap` ->
![[Pasted image 20240708145315.png]]


Case 2 -> 
When hashcode return the same value (now invoke the eqauls( ))

![[Pasted image 20240708145725.png]]


![[Pasted image 20240708145707.png]]


What is the purpose of invoke the `hashcode( )` -> to find where to put the object
What is the purpose of invoke the `equals( )`j -> to find whether it is put or not


How to generate a unique number for class -> 
It is a complex task. So `Object.hash()` is used for it

![[Pasted image 20240708150419.png]]

Note -> `TreeMap` does not use has code. So the `TreeMap` should be implemented from the `Comparabl<Student>`. Tree map use this for sorting. If the class is not implement  from the `Comparable<Student>` then gives a error.

add the github link for this(ss of github)