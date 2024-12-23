There are two way to load the servlet to the ram =>

1.During the Deployment 
OR
2.When get the first request

==Which thread load the servlet==

During the Deployment =>
A thread from a thread pool.

Load when get the first request =>
The same thread that is used for the handle the `HTTP Request` is load the servlet class (thread from the thread pool that is involved to handle the HTTP request )

==What happen when create the instance from the servlet==

After class object is loaded the instance is created (this is created by the application laoder). After run the constructor , then execute a method called `init(ServletConfig)`. During the execution of the init method, servlet is linked to `servlet context`. Now say it graduated to the servlet(Now this works as a servlet)

Same thread is used for the instance creation that is used for the class object loding.

This scenario is same for the both loading type (during w deployment and request)

==What is the class hierarchy of `HTTPServlet`==

![[Pasted image 20240701231224.png]]
=> Explain the How classes are loaded when load the servlet (using above structure)

before laod the MyServlet class object during the resolution processes of the each classes initialization all classes are loaded.

=>Then instance is created using running the constructor of the servlet. 

=>After execute the constructor then `init(ServletConfig)` method is executed. It require a object called `ServletConfig` as the argument

|                                                                          |                                                                                                                                                                                                                                                                                                                                                    |
| ------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the <br>`ServletConfig`                                          | It is object that contains the specific configuration about the <br>servlet and it used to create the link between  servlet context<br>                                                                                                                                                                                                            |
| When `servletConfig` is created                                          | After run the constructor of the servlet  and <br>before execute the `init(ServletConfig)` method                                                                                                                                                                                                                                                  |
| what is `servlet context`                                                | A application has only one servlet context. It is <br>also called as the application context.                                                                                                                                                                                                                                                      |
| What `ServletConfig`<br>contains                                         | -> Contains the configuration of the servlet<br><br>->==servletConfig register the servlet in servlet context and link with the servlet context==                                                                                                                                                                                                  |
| How config object is <br>passed to the `init(ServletConfig)`             | created config object is passed to this method<br>                                                                                                                                                                                                                                                                                                 |
| what happen when the<br>`init(ServletConfig)` is executed                | ![[Pasted image 20240701141456.png]]<br><br><br>![[Pasted image 20240701141248.png]]<br><br>passed config object is stored in the `config` object. Now servlet is linked with the servlet context.Now servlet has created.It can work as <br>servlet<br><br>then execute the `int()` and this method allowed <br>to override in the servlet class. |
| ==What are the ways to <br>register the servlet in <br>servlet context== | There are two ways.<br><br>Static Registration and Dynamic Registration<br><br>Application Server use the `static` registration<br><br><br>Frameworks are used `dynmaic` registration                                                                                                                                                              |
|                                                                          |                                                                                                                                                                                                                                                                                                                                                    |
![[Pasted image 20240701232319.png]]

![[Pasted image 20240701144331.png]]
Above code gives the registered servlet in the serlvlet context

|                                                                              |                                                                                                                                                                                                                                 |
| ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what is the use of <br>`init()` method                                       | Initialization logic can be added to the `init()` method<br><br>                                                                                                                                                                |
| Howmany time<br>`init()` method is <br>executed                              | This is executed only one time. It means only one object <br>is created using the servlet class. Servlet is singleton                                                                                                           |
| How does the <br>application server <br>find the location <br>of the servlet | The web.xml file is not used for this. Servlet context is <br>used for it. <br><br>When create the servlet object it get the details from the <br>logical deployment descriptor. logical DD contains the data<br>of the web.xml |

Summary of servlet loading and initialization->

Servlet can be loading in two ways. 

-> During the deployment
-> When get the first request

==complete this note ==



 