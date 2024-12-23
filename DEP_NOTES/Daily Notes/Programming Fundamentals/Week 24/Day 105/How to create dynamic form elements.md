Form Arrays are used to create dynmic form elements

angular doc -> https://angular.dev/guide/forms/reactive-forms

stepts =>

->create form builder
-> add `ReactiveFormsModeule ` to the import
-> create a form from form builder (including neccessary arrays)
These arrays are used to manage dynamic elements
![[Pasted image 20240731113537.png]]

now bind the form element with form controls and form (data binding) ->

![[Pasted image 20240731114333.png]]

How does the dynamic part is mapped => 

![[Pasted image 20240731115844.png]]

ts -> 
![[Pasted image 20240731115926.png]]

html -> 
![[Pasted image 20240731115947.png]]

Explanation -> 
tr is mapped with the form group that was created from the subject and the marks

Completed data binding -> 
ts -> 
![[Pasted image 20240731120634.png]]

html -> 

![[Pasted image 20240731120722.png]]

![[Pasted image 20240731120738.png]]


Nest define the necessary validtors -> 
![[Pasted image 20240731121830.png]]

How to create custom Validators