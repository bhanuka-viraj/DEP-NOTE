
|                                 |                                                                                                                                                             |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `$("html")`                     | to create a element (html element in this case)                                                                                                             |
| `$("<div>....</div>`            | to create a html content                                                                                                                                    |
| `$().before(jqueryHtml / html`  | to create before a element                                                                                                                                  |
| `$().after(jqueryHtml / html)`  | to create a after a element                                                                                                                                 |
| `$().append(jqueryHtml / html`  | to append to a element                                                                                                                                      |
| `$().prepend(jqueryHtml / html` | to prepend to a element                                                                                                                                     |
| cloning and remove =>           |                                                                                                                                                             |
| `$().clone([true])`             | to clone elements<br>if true is added then event handlers are cloned too.<br><br>By default. It is set to false<br><br>![[Pasted image 20240620125325.png]] |
| `$().remove();`                 | to remove all selected elements                                                                                                                             |
| Replacing =>                    |                                                                                                                                                             |
| `$().html(JQueryHTML,"html")`   | Remove the all content element and add <br>certain elements. <br><br>This is same to the `innerHtml` in web api                                             |
| `$().text("String");`           | This is similar to the inner text in web api                                                                                                                |
| `$().html()`                    | To get the inner html                                                                                                                                       |
| `$().text()`                    | To get the inner text                                                                                                                                       |
| `$().replacewith()`             | To replace the all element with parent element it self                                                                                                      |
| `().replaceAll()`               | do the same as replace with.Syntax is difference<br><br>![[Pasted image 20240620131610.png]]                                                                |
| Attributes =>                   |                                                                                                                                                             |
| `().attr("name","value")`       | to set a attribute                                                                                                                                          |
| `().attr("name):value`          | to get the set attribute                                                                                                                                    |
| `().removeAttr(name)`           | to remove attribute name                                                                                                                                    |
| Property =>                     |                                                                                                                                                             |
| `().prop("name",value)`         | To set the property (value can be anyting<br>no need to be a string like attr)                                                                              |
| `().prop("name):value`          | To get the propety                                                                                                                                          |
