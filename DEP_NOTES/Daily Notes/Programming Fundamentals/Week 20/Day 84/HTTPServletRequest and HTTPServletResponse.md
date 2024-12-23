
![[Pasted image 20240702020225.png]]

This is the class hierarchy of the servlet
![[Pasted image 20240701231224.png]]

#### Step 1

![[Pasted image 20240702020455.png]]

When HTTP Request is sent to the Application server two objects are created. 

These two objects are instance of `HTTPServletResponseIMPL` and `HTTPSerlvetReqeustIMPL` (those are implemented from the `HTTPServletRequest` and `HTTPServletResponse`) this is the hierarchy of the this implementation.These implementation are created by the Specification developers. (application servers). `HTTPServletRequestIMPL` is created collecting the data from the HTTP Request.

These objects are created after getting the HTTP Request. Also these can be created even there is no app is deployed to the Application Server. Only HTTP Request are concerned to create this two object.

![[Pasted image 20240701170912.png]]

`HTTPServletRequestIMPL` implements the `HTTPServletRequest` and it extend the interface `ServletReqeust`

#### Step 2

One Thread is assigned to the handle the HTTP Request (a thread from the thread pool that handle the HTTP Request). Those two objects (created in the above step) are associated with this thread.

What associated means in here ->
This two objects are passed through the all method that is executed from this thread. But in here `Thread Local` is not used for this objects.

In  both `HTTPSerlvetReqeustIMPL` and `servelt context` has a method call `getContextPath( )`.  Thread search which servlet context has the matched path with the path that return from the `getContextPath()` of the  `HTTPSerlvetReqeustIMPL`. When found the matched servlet context, request is sent to it. If there is no matched servlet context then put a error page as a response to the web server.(one servlet context is created for each app)

`getContextPath()` of the `HTTPSerlvetReqeustIMPL` returns the first path segment of the request and the `getContextPath()` of the servlet context return the application context that we set to the application. 

![[Pasted image 20240702020548.png]]

#### Step 3
![[Pasted image 20240702020616.png]]
Now request is in the servlet context (request or execution ??)

`HTTPServletRequestIMPL` has a method called `getServletPath( )`. When it is executed it return the second path segment of the request URL(this is not 100% correct).There is a registry called servlet registry (registry of the servlets of the servlet context) in servlet context and this path is checked with the registry. If there is a matched path then request is send to it. If a matched one not found then invoked the `sendError(404)`  method. If there is a error page defined in the web.xml then it is set as the response to the webserver. If there in no error page is defined then send the default application server error page.

how does the `sendError(404)` works. => 

When  `sendError(404)` method is executed, application server is stopped all the works and check the logical deploy descriptor to find the whether there is a defined error page for this error code.If found it return as the response to the web server. Then web server response it to the client.

![[Pasted image 20240701180514.png]]

#### Step 4

![[Pasted image 20240702020700.png]]
Now continue explanation when thread check the matching servlet path between servlet registry and path that get from the `getServletPath()` of the `HTTPServletRequestIMPL` and found a matching path. 

Then  thread invoke the `service(servelt req, servlet resp):void` method in the servlet instance(this method implemented from the `servlet` interface). Both `HTTPServletRequestIMPL` and `HTTPServletResponseIMPL` are implemented from the `serlvet req` and `servlet resp`. So those objects are fit for the arguments of `service(servelt req, servlet resp):void`. 

![[Pasted image 20240701184108.png]]

This method is implmented in the `HTTPServlet`. This method invoked another method call `service(HttpServlet req, HttpSerlvet resp)` which created in the `HTTPServlet` abstract class. 

![[Pasted image 20240701184509.png]]
This method check the `method` of the request and the invoke the relevant method.
ex -> if the request `method` is `GET` then inovoke the  below method ->

![[Pasted image 20240701184813.png]]

developers responsibility is override the do method with the necessary response.

Then response is wrapped int to the `HTTPServletResponse` int the implementation of the doxx method. It is not necessary to add the reponse int the doxx Mehtod. It can be done during the any phase. (service1 and service2 in the below image)

==NOTE ->== `about thread safe`

If instance properties are used when implement the doxx method thread safe should be used. When the multiple users send the request in the same time multiple thread are created. The best practice is using the local variables and parameters. Because they are default in thread safe. Usage of instance properties should be minimized. 

![[Pasted image 20240702020735.png]]

![[Pasted image 20240702023744.png]]

This the frames of the stack of the thread. After execute the doxx method then start the remove the frames. The moment when the frame before the run() is removed, then instance of  `HTTPServletResponseIMPL` is unwrapped in to a `HTTPRepsonse` and put it in to the web server. Then web server serve it to the client

Then thread is removed from the consume area of the thread pool