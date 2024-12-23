![[Pasted image 20240814135546.png]]
The HTTP request (this contain text) is passed to two zones before become a Request and Response in express js

In Step 1 ->
-> In First layer request is converted into buffer (byte array.). In second layer (HTTP Module) this is converted to a incoming message object. This is also called clientRequest. And also ServerResponse object is created. 

-> Then this two objects (server Response and ClientRequest) are wrapped up by the Request and Response in express Js. The api of the express request added to the object in this stage. URL is taken from the request

In Step 2 -> consult mapping registry

-> Now read the taken URL and find the suitable handler functions (methods) reading the mapping registry. 
-> Now express js invoke the handler function. Devleoper's responsibility is adding the appropriate handler function.

![[Pasted image 20240814134555.png]]

Since the both request and response is passed to the  handlerfunction response object (express response) is created after execute the hadlerfunction. This response is created wrapping up the ServerResponse


In Step 3 -> Creating the HTTP Response 

->Now passed the response object to the HTTP module zone and converted it to the HTTP Response 

->In the last layer the HTTP response is converted to a buffer ( byte array). Then it is sent to the user as a HTTP response.

[[Use Middle Wears in Express Js]]

[[Router in Express Js]]


