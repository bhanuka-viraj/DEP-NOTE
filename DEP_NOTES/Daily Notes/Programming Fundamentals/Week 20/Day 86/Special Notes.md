![[Pasted image 20240703170136.png]]

Only one thread pool have to manage all HTTP Request  in all apps. (In any case there are more than one app has been deployed to the application server)

Servlets in two difference application can have same url pattern. Because right application is being selected first using the context path. (checking the app)



![[Pasted image 20240703170844.png]]

1.First Create the Logical DD

2.Then create servlet context(this is an empty object)

3.Then `Listner Registration` `Filter Registration` `Servlet Registration` are filed in the servlet context getting the infromation from the logical dd.  Still instance are not created from `listenres` `filter` `servlet.`

