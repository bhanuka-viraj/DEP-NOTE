
|                                  |                         |
| -------------------------------- | ----------------------- |
| `$().css("css property","value)` | to set the css property |
| `$().css("css propety")`         | to get the css property |
Dimensions => 
![[Pasted image 20240620142039.png]]

These api can used as setter when a value is passed.
when use the below apit =>

`$(elm).css("width","xxpx")`
`$(elm).css("height","xxpx")`

these works according to the `box-sizing` set


|                                        |                                                                                                                                                       |
| -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| `$(elm).offset():{left,top}`           | give vales relative to the document                                                                                                                   |
| `$(elm).position():{left,top}`         | give values relative to the parent element<br>this similar to the `offlsetLeft` `offsetTop`<br>in web api<br><br>(this api cannot be set as a setter) |
| `$(elm).position({left:200, top:400})` | to set the value top left values <br>relative to the document                                                                                         |
| `(elm).scorllLeft()`                   | to get the scrolled left amount                                                                                                                       |
| ``(elm).scorllTop()``                  | to get the scrolled top amount                                                                                                                        |
add scroll code here =>

|                               |                                                                                                                            |
| ----------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `$(elm).addClass('class')`    | to add class to a element                                                                                                  |
| How to add multiple classes   | ![[Pasted image 20240624111219.png]]<br><br>add the name of the class using a space. Should be added using a single string |
| `$(elm).removeClass('class')` | to remove class from a element                                                                                             |
| `$(elm).hasClass('class')`    | this similar to the contains in web api                                                                                    |
| `$(elm).toggle('class')`      | to toggle class                                                                                                            |
