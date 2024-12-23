|                        |                                                                                                                                                                                                                                                                                                          |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                        | ![[Pasted image 20240212121510.png]]<br>when operands have the difference data type widening primitive conversion is happened.                                                                                                                                                                           |
| Explain this<br>(demo) | ![[Pasted image 20240212122332.png]]<br>                                                                                                                                                                                                                                                                 |
| Explain this           | ![[Pasted image 20240212234722.png]]<br><br>both 7 and 2 are in int data type. so 7 / 2 = 3 and it is int type. The end result of the expression is in double data type. But the result is 6.0. To get the result 7.0 the code should  be like this.<br><br>`System.out.println(7. / 2 * 2.);`           |
| Explain this           | ![[Pasted image 20240212123008.png]]<br>both x2 and y2 are in int data type. so x2 / y2 =  int 5/ int 2 , this is int type 2. The end result of the expression is in double type. But the result is 4.0. To get the result 5.0 code should be like this.<br><br>![[Pasted image 20240213001507.png]]<br> |


How to identify the end result data type after the widening primitive data type.

|  | operand 1 | operand 2 |  |
| ---- | ---- | ---- | ---- |
|  | double | x | double |
|  | float | x | float |
|  | long | x | long |
|  | int | x  | int |
