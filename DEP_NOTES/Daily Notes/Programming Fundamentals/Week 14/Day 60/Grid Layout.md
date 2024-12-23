
|                                     |                                                                                                                                                                                                                                                                                                                                                                                             |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| How to define a <br>grid            | `grid-template-columns` -><br>Define how to columns need to be<br>Rows are automatically created in appropriate way<br><br>`grid-template-rows` -><br>Define how to rows are need to be created<br>columns are automatically created in appropriate way<br>Only one column can be created with several rows<br><br>`grid-template-areas` -><br><br>![[Pasted image 20240515163752.png]]<br> |
| what is the unit<br>`fr` (fraction) | This only used with grid layout<br>To divide the available maximum in to equal parts<br><br>A value can be added to before the `fr` and it is used<br>as a ratio                                                                                                                                                                                                                            |
| What is the use of<br>`repeat()`    | To repeat the column again and again<br>This is only can be used within grid layouts<br>`repeatrepeatitions , size)`<br><br>ex-> `grid-template-columns: repeat(3, 100px);`                                                                                                                                                                                                                 |
| What is the use of<br>`minmax()`    | to set the min max values of the column <br>Only can be used within grid layers<br>                                                                                                                                                                                                                                                                                                         |

![[Pasted image 20240515163354.png]]

|                          |                                      |
| ------------------------ | ------------------------------------ |
| What is a <br>grid track | Area between two adjacent grid lines |

How to create a layout combining both `grid-template-columns` and `grid-template-rows`
shell height and width should be set to the 100%
![[Pasted image 20240515164436.png]]
![[Pasted image 20240515164453.png]]

[[Merges Rows & Columns , Area]]

[[How to create a grid layout to a custom design]]

[[How to create a layout using grid area]]

[[Alignments in grid]]


Summary of the grid
![[Pasted image 20240515184906.png]]