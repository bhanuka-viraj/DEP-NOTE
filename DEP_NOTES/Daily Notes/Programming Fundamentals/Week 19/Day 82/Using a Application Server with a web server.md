
![[Pasted image 20240626122450.png]]

![[Pasted image 20240627022538.png]]
what is the reason to connect application server with a web server =>

Web server is a static server. Only have ability to do some basic static response. (only have ability to send as the response what it has). To do the dynamic response it is required to connect a application server. If it is used with the java these are the options for the application servers ->
`Jakarta EE Full platform`
`Web profile/containers`
`Servelet Container`

what are the task that cannot handle web servers it self->

`Dynamic Responses`
`Database related operations`
`File related Operations`
`Server-server communication`

connecting a web server to a application server is a complex task. Hence a default web server  comes with the application server

==what is the use of `jakarta servelt` =>==

 servlet in the app get the HTTP request from the web server and create the response and give it back to the web server. Now web server can send the response to the client side. `jakarta servelet` involve the HTTP request and response manipulation in this process 