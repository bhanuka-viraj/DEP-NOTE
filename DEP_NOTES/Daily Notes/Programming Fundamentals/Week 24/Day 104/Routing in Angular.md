Angular routes are created base on the `hitory api`. There are two way to handle routing in angular. That is when use with the ng modules and without ng modules

## Routing in Angular without ng modules

![[Pasted image 20240729133111.png]]

`app config` ->
![[Pasted image 20240729133122.png]]

routes should be added to the routes in `provideRoutes(routes)`

 What are the services that are registered in the context when activate the route
 1.Router Service
 2.Activated Route Service

![[Pasted image 20240729133442.png]]


|                               |                                                             |
| ----------------------------- | ----------------------------------------------------------- |
| What is the router<br> outlet | This is a special ng component that can have several stages |
 How to determine paths -> (login and main)
![[Pasted image 20240729140942.png]]

This is the component empty part statement 
![[Pasted image 20240729141253.png]]

![[Pasted image 20240729141339.png]]

How to use redirect -> 

![[Pasted image 20240729141453.png]]

[[Redirect in Angular Route]] -> How does the redirect works in the angular routes

[[Child Routes in Angular]] -> How does the child routes work in angular routes




## Routing in Angular with ng modules

Angular already create a ngModule for routines, but they recommend to create a new ngModule for routine

How to set routes -> 

create routes in the `app.module.ts` => 
(this should be done in the `AppRoutingModule`)
![[Pasted image 20240729182741.png]]

import `RouteModuel` to the `app.moudle.ts`
(this should be done in the `AppRoutingModule`)
![[Pasted image 20240729182818.png]]

![[Pasted image 20240729184824.png]]

What is the difference between `RoutereModule.forRoot()` and `RouterModule.forChild()` => 

There are two services (`Router Service`, `Activated Route Service`) that need to be added to the the context when create the router service. using `RoutereModule.forRoot()` and `RouterModule.forChild()`  is used to determine seriveces are going to added for the which context.

`RoutereModule.forRoot()` -> two services are added to the root context
![[Pasted image 20240729183940.png]]

`RouterModule.forChild()` -> two services are added to the it's ng modules context

What is the module with providers -> 

![[Pasted image 20240729183732.png]]

Routes should be added in the `app-routing.modules.ts` Not in the app module.
![[Pasted image 20240729185357.png]]


How to redirect when the path is not found -> 


this route should be added at the end of the route list 
![[Pasted image 20240729192441.png]]