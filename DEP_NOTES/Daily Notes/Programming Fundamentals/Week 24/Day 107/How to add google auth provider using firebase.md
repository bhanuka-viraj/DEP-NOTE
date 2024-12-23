
->firebase documentation
https://firebase.google.com/docs/auth/web/google-signin

-> github link for example 
https://github.com/angular/angularfire/tree/main/samples/modular/src/app


with this code pop screen comes to choose the select the google account

![[Pasted image 20240801132041.png]]

![[Pasted image 20240801132147.png]]

This check whether already logged or not, If logged directly return the true if not logged then direct to the user login

Q.What is the reason to use promise?
A. This might take some time firebase to get the result from the back end to whether use log or not.This why promise is being used

![[Pasted image 20240801134201.png]]

what does `onAuthStateChangede()` -> 
This a event listener that works for the change state of the authentication. When sign in ,sing out this works. In our case it is not necessary to set a event listener every time login and logout. We only need in initially. So we need to unsubscribe after use in initially. Every time user go to the main view , a new event is set

How to handle this case -> 

Service is used here. It is singleton. The constuctor is executed only once. So constructor is used to get the authState
