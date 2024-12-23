
-> Spring Web is associated with the spring core and cannot use stand alone without spring core

|                                                                                                                              |                                                                                                                                                                                                                                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Is there a <br>main method in <br>spring web <br>`WebAppInitializer`<br>class                                                | No. There is no main method in this class. Web app is<br> deployed to a application server <br><br>Also there is no web server in spring web unlike nest<br>or express. Because web server in application server.<br>Not in spring web<br>                                                          |
| What does spring<br>web is used internally                                                                                   | ->It is used servlets. Dispatcher servlet is used internally<br><br>-> If the dispatcher servlet in sot configured wit the <br>spring web, then it is not worked properly                                                                                                                           |
| How to register the <br>dispatcher servlet in<br>servlet context                                                             | There are two ways to register servlet in servlet context<br>-> statically<br>-> Dynamically<br><br>Spring use dynamic servlet registration. Identify the <br>moment that deploy the web application and register <br>the dispatcher servlet in servlet context when the<br>application is deployed |
| How to identify when<br>the web application <br>is deployed                                                                  | `ServletContainerInitializer`<br>Is the best way to do it<br><br>`onStartUp()` method is override in the above class<br><br>-> Also listeners can be used. But this might give the wrong answer                                                                                                     |
| What is the class <br>that is used to <br>identify when the <br>dispatcher class is <br>registered in the<br>servlet context | `AbstractAnnotationConfigDispatcherSerevletInitializer`                                                                                                                                                                                                                                             |
|                                                                                                                              |                                                                                                                                                                                                                                                                                                     |


==Q.== What happen when the web application is deployed 

==A==. 

![[Pasted image 20240830215857.png]]

A instance of `WebAppInitializer` is created by the application server. Two instance of `AnnotationConfigWebApplicationContext` are created and those are extend with the `AnnotationConfigApplicationContext`. Also `DispatcherServlet`  is created. Those two `AnnotationConfigWebApplicationContext` are connected each other. Both context are required configuration classes.  

==Q.== How the configuration classes are given to the two `AnnotationConfigWebApplicationContext` 

==A.== There are two methods in the `WebAppInitializer` to  give those configurations to the context. (Those methods are in the `AbstractAnnotationConfigDispatcherSerevletInitializer` and they are extended to the `WebAppInitializer`)

==methods -> ==
![[Pasted image 20240830220936.png]]

|                                                                                                                         |                                      |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| What are the methods <br>that are used to set the <br>configuration for the <br>`AnnotationConfigWebApplicationContext` | ![[Pasted image 20240830220936.png]] |

Q. What is the relationship between `WebRootContext` and the `WebAppContext` 

![[Pasted image 20240830221523.png]]

A. `WebRoot Context` is the parent class of the `WebApp Context`

==Q.== How does the  `WebRootContext` and the `WebAppContext` are worked
==A.== Those context are factory. `WebRootContext` factory is the parent factory of the `WebAppContext` factory. When a instance is searched in the `WebAppContext` and if it is not available in the `WebAppContext` then searched in the `WebRootContext`.




|                                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the reason <br>to having two context.<br>                  | reason to having two<br>`AnnotationConfigWebApplicationContext`<br><br>Two context are used to improve the cohesion<br><br>`WebRootContext` -> <br>task related to business and data access<br>(service layer and repository) are assigned to<br>this context<br><br>`WebAppContext` -><br>task related to web applications are assigned<br>to this context<br><br>Note -> <br>If all task are done withing the single context<br>then cohesion is high(coupling is high). Two <br>context are used to reduce the cohesion |
| What is the purpose <br>of using annotation<br>`@ResponseBody`     | This denote response is also included with this                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| What is the meaning<br>of the annotation<br>`@RestController`      | This is used represent the both annotation<br>`@ResponseBody` and the `@Controller`                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| What is the use of <br>`@EnableWebMvc`<br>annotation               | If this is not added to the config class , converters <br>might not works properly                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| How to determine <br>path variable in spring<br>web                | ![[Pasted image 20240831133154.png]]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| How to access to the<br>path variable within<br>the handler method | ![[Pasted image 20240831133335.png]]<br><br>if the defined parameter for the path variable in the <br>method is not  same as the path variable in the path<br>then define the path variable as this -><br><br>![[Pasted image 20240831133602.png]]                                                                                                                                                                                                                                                                         |
|                                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
[[Convert the request body to a java object]]

Note -> There could be a error when use the spring 6
`# [Name for argument of type [java.lang.String] not specified. Ensure that the compiler uses the '-parameters' flag](https://stackoverflow.com/questions/78009630/name-for-argument-of-type-java-lang-string-not-specified-ensure-that-the-comp)`

link for stack overflow ->
https://stackoverflow.com/questions/78009630/name-for-argument-of-type-java-lang-string-not-specified-ensure-that-the-comp

add this to pom.xml file
![[Pasted image 20240831135330.png]]


|                                                                                            |                                                                                                                                                                                                                                                                                               |
| ------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| How to set the http <br>status code                                                        | ![[Pasted image 20240831135730.png]]<br><br>when set the `HttpStatus.CREATED` as the response status<br>201 was set as the status code                                                                                                                                                        |
| How to handle<br>request when <br>request type is<br>applciation/x-www-<br>form-urlencoded | It is required to set two difference methods to handle the <br>json and the applcation/x-www-form-urlencoded. Then <br>make following changes<br>![[Pasted image 20240831141206.png]]                                                                                                         |
| How to get the <br>data from the<br>query string of <br>request                            | create a string variable that similar to the query string<br><br>![[Pasted image 20240831141903.png]]<br><br>![[Pasted image 20240831141823.png]]<br><br>if the query parameter and the argument is not same<br>use `@RequestParam` parameter<br><br>![[Pasted image 20240831142436.png]]<br> |
|                                                                                            |                                                                                                                                                                                                                                                                                               |
