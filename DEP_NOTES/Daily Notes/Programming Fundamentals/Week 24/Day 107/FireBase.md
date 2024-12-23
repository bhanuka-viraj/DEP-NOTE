|                                                                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ----------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the difference<br>between software <br>security and application<br>security | `Software Security->`<br>Security is Coupled with the software.addressing security across the entire software system and its environment.<br><br>`Application Security->`<br>Security is not coupled with the software. App is created intergratale to application security                                                                                                                                                        |
| What is the reason to<br>use application securtiy                                   | Application security is preferred over software security for authentication because it specifically addresses application-level threats, implements advanced authentication protocols, adapts to dynamic security needs, ensures detailed user and session management, and complies with industry standards like OWASP. This specialized focus ensures more robust and context-aware protection for user authentication processes. |
| What are the examples for  application security                                     | -> Google firebase<br>-> Auth o<br>-> keyCloack<br>-> WSO2 Iam<br>                                                                                                                                                                                                                                                                                                                                                                 |
| What is multi-platform sign in                                                      | Allowing to sign-in using already singned account like  google,facebook,twitter, github,<br>                                                                                                                                                                                                                                                                                                                                       |
| How does the firebase allow multi platform sign in                                  | Multi platform is complex task and have to study lot of documentation. But Firebase allow to do this very easily                                                                                                                                                                                                                                                                                                                   |
++first register a web app in Firebase ->

++Enable the authentication in Firebase web app->
build -> authentication

++then integrate the created web app wit the angular -> 

How to connect angular application with Firebase -> 
-> https://github.com/angular/angularfire/blob/main/docs/install-and-setup.md

install Firebase to the angular (angular-fire)using -> `ng add @angular/fire` and proceed the steps
(This integrate the angular project with the Firebase)


after Firebase installed in angular  config the Firebase using app-config
++ This is access the enabled authentication in Firebase from the angular project

`provideAuth(() => getAuth())`

![[Pasted image 20240801124056.png]]

[[How to add google auth provider using firebase]]


add GitHub link -> https://github.com/IJSE-Direct-Entry-Program-12/angular/tree/main/ng-firebase-todo-list

