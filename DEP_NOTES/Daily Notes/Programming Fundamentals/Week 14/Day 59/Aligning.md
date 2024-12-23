
|                                                                                         |                                                                                                                                                                                                                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| align a inline element<br>horizontally within the<br>block (also for text)              | `text-aling:`                                                                                                                                                                                                                                                               |
| align a block horizontally<br>within a block                                            | `margin-left: auto;`<br>`margin-right: auto;`<br><br>to use this width should be specified.<br>this not work vertically if<br>`margin-top: auto`<br>`margin-bottom:auto`                                                                                                    |
| what are the `trnasform:`<br>functoins<br>                                              | `translateX()`<br>`translateY()`<br>`trnaslate`<br>`ScaleX(float)`<br>`ScaleY(float)`<br>`Scale(x,y)`<br>`rotateX(deg)`<br>`rotateY(deg)`<br>`rotate(x,y)`<br><br>In here percentage can be used.But in here <br>percentage get relative to itself rather<br>parent element |
| What is the difference <br>between `left:100px`and <br>`transfrom:transformX()`<br><br> | consider this example<br>`left:50%` -> This 50% of the parent width<br>`trnaform:translateX(50%)`-><br>This is 50% of the element itself width<br><br>![[Pasted image 20240514183509.png]]                                                                                  |
| does transform work<br>with inline                                                      | No.<br>In order to use transform with `inline`<br>it is required to convert to the `inline-block`                                                                                                                                                                           |
| What is the<br> `vertical-align`<br>                                                    | to align the vertically <br>Works with inline elements and table<br>data                                                                                                                                                                                                    |
[[Transform with Fixed]]

How to aligning is done by using transform

![[Pasted image 20240514184145.png]]

![[Pasted image 20240514184211.png]]
How to align using when the position is absolute
![[Pasted image 20240514185822.png]]

![[Pasted image 20240514185836.png]]
