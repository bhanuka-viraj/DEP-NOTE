
Angular disable the default validation in HTML 5 and take the control of validation. 

![[Pasted image 20240730125041.png]]
Form module need to be added



There are six css classes that are added to the input element by the angular. It is necessary to add the `[(ng-model)]` to get those classes. Only 3 classes added to the input at once base on some conditions.

![[Pasted image 20240730121305.png]]

|                                                                       |                                                                                                                                                                                       |
| --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what are the classes<br>that added by the ng forms <br>for validation | `ng-prisitine` <-> `ng-dirty`<br>`ng-untouched` <-> `ng-touched`<br>`ng-valid` <-> `ng-invalid`                                                                                       |
| `ng-prisitine` <-> `ng-dirty`                                         | `ng-prisitine` -><br>if the initial values is not changed<br><br>`ng-dirty` -> <br>if the initial value is changed. Even it get back to <br>the initial value                         |
| `ng-untouched` <-> `ng-touched`                                       | `ng-untouched` -> Can be comes the focus to <br>element , but focus not gone and still with the <br>element<br><br>`ng-touched` -> If focus comes to the element <br>and then go away |
| `ng-valid` <-> `ng-invalid`                                           | `ng-valid` -> If the values is matched with the <br>added pattern<br><br>`ng-invalid` -> If the value is not matched with <br>the added pattern                                       |
add required to the input element otherwise not validate when value is empty

![[Pasted image 20240730121946.png]]

How to mark the input element mark as dirty when the button is clicked -> 


![[Pasted image 20240730123109.png]]


What are the advantages of using `[(ngModel)]` =>

->Two Way data binding
-> HTML 5 Validation API
-> CSS Classes (six css classes for the validation)


==How to use `[(NgModel)]` with multiple form elements within Form element==

![[Pasted image 20240730125408.png]]
![[Pasted image 20240730125523.png]]

This gives a error when  `[(ngModel)]` is used with the form element

explanation ->
When form is used with the `[(ngModel)]` those validation six classes are added to the `form` too. This classes are denote the whole validation of the form. Reason for the error is method of identification of the form element by the form should be defined. When form element are named usgin `name` attribute the error is gone and form can identify the form element. Also for element can be define as the stand alone form element and then they are not considered by the form for overall for validation. 

![[Pasted image 20240730130545.png]]

How does the css classes mean now -> 

`ng-dirty` -> If at least one form element is dirty then whole form is dirty
`ng-invalid` -> If at least one form element is invalid then whole form is invalid
`ng-touched` -> If at least one form element is touched then whole form is touched
same rule for the other CSS classes

==Q. ==What Happen to the css classes when the form is reset (using reset type clear button)

![[Pasted image 20240730131841.png]]

==A.== Css classes are also reset (set to the initial values)


==Q==.How to use the bootstrap classes with the `[(ngModule)]`

![[Pasted image 20240730133402.png]]

==Q.==How to set the dynamic invalid messages 

==A.== 
![[Pasted image 20240730133946.png]]

When ID is empty -> 
![[Pasted image 20240730134213.png]]

When ID is invalid -> 
![[Pasted image 20240730134138.png]]

`hasError('error code')`

error code should be validation constraints attribute name (`required`, `pattern`....)

when deal with three validations => 

![[Pasted image 20240730134745.png]]

==Q.== How to validate the form?
==A.== `(ngSubmit)` should be used to get the overall validation of the form

![[Pasted image 20240730135338.png]]

![[Pasted image 20240730140031.png]]
`ngForm` returns a object that include the whole data of the form input elements 

![[Pasted image 20240730135731.png]]

==Q.== What is the reason to use `touched` rather than `dirty`.
==A.== This is a good practice that is used in the industry. Now validation messages only show when the focus is changed to a another form element

