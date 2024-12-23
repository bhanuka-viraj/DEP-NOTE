How to to use reactive forms => 

First create form control instance and bind it with the html form element. Now angular has the control of the html form element

=>Create the control instance
![[Pasted image 20240730165214.png]]

 =>connect the form controller with the html form element
![[Pasted image 20240730165226.png]]

=> Set the validation attribute the validator
![[Pasted image 20240730170051.png]]

Note -> Since this is also used ng module internally all css classes that were available in the `template-driven-form` also available in here too.

==Q.== How to use the form with `reactive forms`
==A== This is allowed to track the all form element as a form.

create a form group in the ts file. Now set the form controller to this group.Now whole form in html is set bind with the form group.  

Create the form group =>
![[Pasted image 20240730172102.png]]

bind the form group with the html form =>
![[Pasted image 20240730172202.png]]
==note== => Now allow to access the form controllers from the HTML form using their names using `formControllerName`

![[Pasted image 20240730172631.png]]

To set the bootsrap classes for validation can be used as the previous way-> 
In following code class binding through a object is used to minimize the boiler plates => 

[[class binding in angular]]  => Create this note 

![[Pasted image 20240730174752.png]]

![[Pasted image 20240730174721.png]]

How does this works -> when invoked the `getClasses("id")` CSS classes `is-valid` or `is-invalid` is return if the corresponding boolean value is true. (key:value)

How to set the validation message -> 

This is same as the `template-driven-forms`

![[Pasted image 20240730180256.png]]

![[Pasted image 20240730180315.png]]

![[Pasted image 20240730180334.png]]

accessing all the time using `frm.get()` js accessor properties are used 

![[Pasted image 20240730185530.png]]

![[Pasted image 20240730185548.png]]

![[Pasted image 20240730185608.png]]

[[What are the property type of the js object]]


==Q.== How to use form builder service -> 
==A.==  This is used to simplify the code of `ReactiveFormComponent`

![[Pasted image 20240730192559.png]]

When using this it is not required to create a new form group and new form controller

==Q.==How to  create a custom validator when using the `reactive forms`

==A.==

First new class should be created. 

|                                           |                                                                 |
| ----------------------------------------- | --------------------------------------------------------------- |
| How to create  a <br>new class in angular | `angular generate class <cls namee>`<br>`ng g class <cls name>` |
|                                           |                                                                 |
create this function in created class => 

![[Pasted image 20240730194145.png]]

[[How to create dynamic form elements]]
