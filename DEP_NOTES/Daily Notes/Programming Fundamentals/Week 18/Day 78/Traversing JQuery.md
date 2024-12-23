
|                           |                                                                                                                                                      |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| `prev()`                  | to traverse previous element                                                                                                                         |
| `next()`                  | to traverse next element                                                                                                                             |
| `paraent()`               | to traverse the immediate parent element                                                                                                             |
| `parents('css selector")` | this is similar to the `closets` in web api<br>to traverse the any parent                                                                            |
| `children()`              | to traverse the to the children.<br>this give all the childrens                                                                                      |
| `children().get(index)`   | to get a particular children<br>this return html element.This should be wrapped <br>with the `$`<br>ex -> `$(li2Elm.parent().children().get(3))`<br> |
| `find(css selcetor)`      | this is simillar to the `element.querySelector()`<br>in web api                                                                                      |

