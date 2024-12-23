

### Selectors

| `*`                                                      | This is universal selector                                                                                                                                                                                                                                                                                                                                                                                                               |
| -------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the difference <br>in this two                   | ![[Pasted image 20240513150307.png]]<br>and<br>![[Pasted image 20240513150328.png]]<br>refer this html<br>![[Pasted image 20240513150542.png]]<br><br>when use the body as the selector rules are applied to <br>body and other element get the properties because of<br>cascade<br><br>When use the `*` as the selector all the element are <br>applied the properties separately (apply to the all `h1`, <br>`ul` and `li` separately) |
| What is the specificity <br>of the universal<br>selector | Specificity of the `*` is zero                                                                                                                                                                                                                                                                                                                                                                                                           |
| `ID` seletor (`#`)                                       | Should be unique to the page. Rendering engine allow to use the same id identically. But is not a best practice<br><br>Id is used for uniquely identify<br>                                                                                                                                                                                                                                                                              |
| `Class` Selector `(.)`                                   | Class is used to group the element                                                                                                                                                                                                                                                                                                                                                                                                       |
| `attribute` Selector<br>`[]`                             | attributes of the element are used as the selector<br><br>what is the syntax -><br><br>`[class]` -> select the element that used the class atribute<br><br>`[class="abc"]` -> select the element where class is <br>equal to the 'abc'<br><br>==What is the purpose of using attributes==<br><br>to set the meta data<br><br>                                                                                                            |
| `Type`  Selector<br>`html tag name`                      | html tag name is used as the type selector in here.<br>`p`, `h1` , `div` like wise                                                                                                                                                                                                                                                                                                                                                       |
| What is the grouping <br>selector                        | `,` is used to group selectors but It is neither a <br>combinator or selector                                                                                                                                                                                                                                                                                                                                                            |
|                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                                          |

### Combinators

|                                         |                                                                                                    |
| --------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `Descendant`<br>combinator<br>(`space`) | to specify the any element in within the sub element (doesn't care the direct or undirect element) |
| child combinator <br>(`>`)              | to specify the direct element of the sub element                                                   |

![[Pasted image 20240513234145.png]]
`ol > li > ul > li > span{

}`
this also can be denoted like this
`ol ul span {

}`

|                                      |                                                                                                                                  |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| `adjacent sibling`<br>combinator `+` | To select the adjacent sibling of a element<br>(adjacent sibling in the right side)<br><br>This is also called as `next` sibling |
![[Pasted image 20240513234245.png]]
The are 4 paragraph to select


|                                     |                                                                                                 |
| ----------------------------------- | ----------------------------------------------------------------------------------------------- |
| `general sibling`<br>combinator `~` | To specify the all sibling in the right side.<br><br>This is also called as `subsquent sibling` |
|                                     |                                                                                                 |
![[Pasted image 20240513234325.png]]
All three paragraph in the nested div right side to the div.

|                                                                                   |                                                                                                                                                                                                                                                                                                                                                                                                   |
| --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What are the simple selector,<br>compound <br>selectors and <br>complex selectors | Simple Selector -><br>only use simple selectors<br>`#abc{<br>}`<br><br>`#abc,#ed{<br>}`<br><br>Compound Selector-><br>use several simple selectors<br>this is commonly used to increase the specificity<br>`div.abc{<br>}`<br><br>Complex Selectors-><br>use combinators<br><br>`div ul>li{<br>}`                                                                                                 |
| What is the nested selector<br>This is a new selector<br>(this is CSS 3 feature)  | ![[Pasted image 20240513183127.png]]<br>This can be represent using nested seletor like <br>like this<br><br>![[Pasted image 20240513183310.png]]<br><br>Now this can simplified using another nested<br>selector<br><br>![[Pasted image 20240513183756.png]]<br>`&` can be used but it is not necessary to use<br><br>![[Pasted image 20240513184039.png]]<br><br>This is called nested CSS Rule |

