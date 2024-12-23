
|                                                 |                                                                                                                             |
| ----------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| What was the main<br>purpose of flex            | 1. To use column<br>2.To aligning<br>3.Responsive designing                                                                 |
| How to turn a block<br>element to a flex<br>    | `display:flex`<br><br>                                                                                                      |
| How to turn a inline<br>element to a flex       | `display:inline-flex`                                                                                                       |
| What happen when<br>element turn into a<br>flex | The element itself work as a block or element. But it's<br>content now behave as flex layout rather a normal flow<br>layout |

What is the meaning of these attributes->

|                       |                            |
| --------------------- | -------------------------- |
| `display:flex`        | block + flex layout        |
| `display:inline-flex` | inline  + flex layout      |
| `display:block`       | block + normal flow layout |
| `display:inline`      | inlne + normal flow layout |

|                                                                            |                                                                                                                                                |
| -------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the meaning <br>of a flex line                                     | flex line lay same direction on the main axis.If there is no <br>space to placed the element in the flex line then add a <br>new flex line<br> |
| what is the property<br>`flex-direction`                                   | This the direction that main axis is being placed<br>In default flex-direction is the `row`                                                    |
| How to change the <br>`flex-direction`<br>(direction of the <br>main axis) | `flex-direction:row`<br>`flex-direction:row-reverse`<br>`flex-direction:column`<br>`flex-direction:column-reverse`                             |

![[Pasted image 20240515125304.png]]

|                                 | How does the flow-direction works    |
| ------------------------------- | ------------------------------------ |
| `flex-direction:row`            | ![[Pasted image 20240515124040.png]] |
| `flex-direction:row-reverse`    | ![[Pasted image 20240515124100.png]] |
| `flex-direction:column`         | ![[Pasted image 20240515124128.png]] |
| `flex-direction:column-reverse` | ![[Pasted image 20240515124203.png]] |

[[Flex Item Properties]]
[[Flex properties for aligning]]
[[Flex wrap property]]

|                                               | flex-flow                                                                 |
| --------------------------------------------- | ------------------------------------------------------------------------- |
| What is the use<br>of `flex-flow`<br>property | This is a short hand property for the `flex-direction` and<br>`flex-wrap` |




|                                        | gap                         |
| -------------------------------------- | --------------------------- |
| How does the<br>gap work               | `row-gap:`<br>`column-gap:` |
| what is the <br>short-hand<br>property | `gap:`                      |

summary for the flex properties->

![[Pasted image 20240515135042.png]]
