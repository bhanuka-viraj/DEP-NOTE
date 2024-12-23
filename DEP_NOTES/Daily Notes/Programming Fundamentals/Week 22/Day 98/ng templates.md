In Angular, `ng-template` is a powerful directive that allows you to define template fragments that are not rendered directly by default. Instead, these templates can be rendered programmatically or conditionally at a later time. It provides a way to create reusable and dynamically modifiable parts of the UI.

What is the reason to use `ngTemplates` -> 
This is used to works with structural directives. When a html element is wrapped up with a`<ngTemplates>` it is removed from the DOM.

Syntax to use `ngTemplate` for as the else. 

This is the old syntax =>

![[Pasted image 20240718135013.png]]

![[Pasted image 20240719081927.png]]

When the boolean expression is true element is display and ng-tamplates was hidden . When the boolean expression is false element is hidden and the ng-template is displayed

![[Pasted image 20240718134821.png]]
