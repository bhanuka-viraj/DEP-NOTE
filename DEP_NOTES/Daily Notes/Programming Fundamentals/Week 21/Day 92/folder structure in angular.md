
|              |     |
| ------------ | --- |
| angular.json |     |
| pakage.json  |     |
things to change in angular.json -> 

Ther are only three things to change

Angular.json file ->


![[Pasted image 20240711204830.png]]

==assets== -> static assets ( images, videos)
![[Pasted image 20240712114639.png]]


==styles== -> refer the main css file. Can be added some additional css if necessary. Also can be import the additional css in to the main css file.

![[Pasted image 20240712115039.png]]

package.json file -> 

`start : ng build` -> build the necessary way to match the production
`start : ng serv` -> necessary way to the match the development

|                                                                  |                                                                                                                                                                                                                                  |
| ---------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is component in<br>angular                                  | User interface parts<br><br>there are four files in the components<br><br>->ts (to write logic in UI)<br>->html (to create the structure of the UI)<br>->css (the type we selected initially)<br>->spec.ts (this is for testing) |
| Is is allowed to use <br>multiple style sheet <br>to a component | Yes. It is allowed to use more than one css file to component                                                                                                                                                                    |

Note ->

-> In Angular think logic and the presentation should be separated. So HTML and Type script is provided separately

-> In React they believe logic and the presentation should not be separated. So they provide 
`js + xml -> jsx`
`ts + xml -> tsx`


==Component.ts file ->==
TypeScript class that defines the behavior and logic associated with a specific Angular component

![[Pasted image 20240711210931.png]]

|                                               |                                                                                                |
| --------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| What is selector                              | name of the component                                                                          |
| what does template <br>means<br>(templateUrl) | it means the html<br><br>in this htm file allowed to use html and angular specific<br>syntaxes |
|                                               |                                                                                                |

==appmodule.ts fle ->== This is the root module of the application.
![[Pasted image 20240711211129.png]]


