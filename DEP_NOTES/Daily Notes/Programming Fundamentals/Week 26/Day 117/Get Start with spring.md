
|                                                            |                                                                                                            |
| ---------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| What are the main 3<br>components of spring <br>frame work | 1.Web<br>2.Core Container<br>3.Data Access / Interagration<br><br>![[Pasted image 20240816092132.png]]<br> |
|                                                            |                                                                                                            |



![[Pasted image 20240815222202.png]]

![[Pasted image 20240816092224.png]]

git link for example -> https://github.com/Yasith-s-play-ground/spring-example

|                                                          |                                                                                                                                                                                                                                                                                                                              |
| -------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what is spring                                           | Spring do the factory design pattern<br><br>spring like a large factory                                                                                                                                                                                                                                                      |
| what is the meaning <br>of this                          | `AnnotationConfigurationApplicationcontext`<br><br><br>this context get the detail through the anntotation<br>                                                                                                                                                                                                               |
| What is a configureation <br>class                       | [[Bean definiton source]]<br><br>the required knowlege to create object in spring context<br>                                                                                                                                                                                                                                |
| How to create a spring<br>context                        | ![[Pasted image 20240816091414.png]]                                                                                                                                                                                                                                                                                         |
| How to register <br>app config  in to <br>spring context | `ctx.register(AppConfig.class)`<br><br>what happens -> <br>instance of the appconfig is created and the put into <br>the spring context                                                                                                                                                                                      |
| What is the meaning <br>of `@component`                  | that marks a Java class as a Spring-managed component. This means that Spring will automatically detect the class and register it as a Spring bean during the component scanning process.                                                                                                                                    |
| What is the<br>use of <br>`@componentScan`               | <br>In Spring, `@ComponentScan` is an annotation used to specify the base packages that Spring should scan to find and register beans, which are classes annotated with `@Component`, `@Service`, `@Repository`, `@Controller`, or other stereotype annotations.                                                             |
| What does happen with the `@Autowired`                   | ![[Pasted image 20240815222813.png]]<br><br>In Spring, the `@Autowired` annotation is used for dependency injection. When you apply `@Autowired` to a field, constructor, or setter method, Spring automatically injects the appropriate bean into that field or method, reducing the need for manual dependency management. |
|                                                          |                                                                                                                                                                                                                                                                                                                              |




