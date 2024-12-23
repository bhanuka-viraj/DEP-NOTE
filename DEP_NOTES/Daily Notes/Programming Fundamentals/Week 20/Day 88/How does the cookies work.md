
![[Pasted image 20240705135851.png]]



3 and 5.When client is connected with the server (after verify the username and password)  a session object is created in server side with the a unique id

6.When server send the response to the client `set-cookie` is added to the header with thee session id.

7.Then session id is stored in the session database. This is a encrypted data base.

![[Pasted image 20240705142948.png]]

8/ 9.Now Request is sent to the server side adding the previously saved cookies (session id) to the `Cookie:SesionId = xxxx` in header. Now all request are send adding the cookie

10.Then in server side inspect the session objects in the server.

11.If there is not matched cookies with the session id the response to the server a 401 not found error.

12.If there is matched cookies then send the required response

13 / 14.When client side asked for the logout then relevant session object in the server side is invalidate.

14.Still previous cookies are send to the server side but now they are invalidated. So server not found the valid session object.


