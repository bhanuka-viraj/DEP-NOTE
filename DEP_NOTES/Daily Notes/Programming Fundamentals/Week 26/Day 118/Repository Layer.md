
![[Pasted image 20240816121503.png]]

|                                                |                                                                   |
| ---------------------------------------------- | ----------------------------------------------------------------- |
| How to organize<br>the repository              | base on the relation                                              |
| What is the reason to <br>user crud repository | ![[Pasted image 20240816120706.png]]<br><br>This is a boiler code |
|                                                | [[Generic programming]]                                           |
|                                                |                                                                   |
Curd Repository is used to avoid those boiler plates ->

Crud Repository -> 

![[Pasted image 20240816121515.png]]

How does the repository layer is organized -> 

![[Pasted image 20240816130706.png]]


|                                                                                                               |                                                                                                                                                                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| how does the <br>`dependency inversion`<br>and <br>`interface segregation`<br>is used in the repository layer |                                                                                                                                                                                                                                                                               |
| What is the `factoryDesignpattern`<br>and <br>`factoryMethodDesignPattern`                                    | `factoryDesignpattern` => <br><br>a singleton factory is designed and it gives the products.<br><br>factory instance should be created to get the product<br><br>`factoryMethodDesignPattern` =><br>methods are gives the products<br><br>factoryDesignPattern is mostly used |
| What is the reason to user <br>query repository                                                               | Join queries are done in here. If a join query<br>are done in a one particular impl repository<br>the cohesion is decreased.<br><br>anything that common to the all repository <br>are added in the query repository                                                          |
|                                                                                                               |                                                                                                                                                                                                                                                                               |

![[Pasted image 20240816143320.png]]