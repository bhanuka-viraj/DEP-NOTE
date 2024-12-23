

![[Pasted image 20240731175443.png]]


![[Pasted image 20240731180027.png]]
`#h1` and the `#crazy` are the template reference in here

|                                                  |                                                                                                                              |
| ------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| What is the use of<br> content reference varible | Allow to access within the html file and also in ts file                                                                     |
| How to access from ts                            | using `@ViewChild`. Template reference should be<br>passed to the `@ViewChild()`<br><br>![[Pasted image 20240731180635.png]] |
|                                                  |                                                                                                                              |

How to access the all element when there are several content elements and view elements 

this not working ->
![[Pasted image 20240731194535.png]]
This only allow to access to the first element 

![[Pasted image 20240731194602.png]]
using following way to achieve this

![[Pasted image 20240731194924.png]]

![[Pasted image 20240731194937.png]]