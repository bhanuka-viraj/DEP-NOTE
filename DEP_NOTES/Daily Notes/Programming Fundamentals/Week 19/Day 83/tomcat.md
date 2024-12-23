#### Start and Config Tomcat server

How to start tomcat =>

run this command `startup.sh`

Follow this step if tomcat denied permission when command `startup.sh`
![[Pasted image 20240627121835.png]]

follow this command in tomcat installed location
`opt/sdkman/candidates/tomcat/`
![[Pasted image 20240627121813.png]]


How to set the password =>

open the `tomcat-user.xml` file using nano
![[Pasted image 20240627123104.png]]

add the commented user name and password at the end of the doc and changed as we need. then save and exit. (ctr + 0 for save)
![[Pasted image 20240627123013.png]]

Then shutdown and start the server again

![[Pasted image 20240627123329.png]]

There are two way deploy using tomcat =>

1.Using web interface 

2.Adding war file to this directory => 

![[Pasted image 20240627123919.png]]
this will automatically deploy when server is started

#### Use Tomcat

What is the reason to scope is provided in here
![[Pasted image 20240627133013.png]]

complete this ->
provided means only dependency available during compile. 


How to set the pom.xml file when use the tomcat =>

set java 17 as the version 
![[Pasted image 20240627133357.png]]


ad the packaging as war

![[Pasted image 20240627133418.png]]

get the artifact name for the build 

![[Pasted image 20240627133453.png]]

complete pom.xml =>

```xml
<?xml version="1.0" encoding="UTF-8"?>  
<project xmlns="http://maven.apache.org/POM/4.0.0"  
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">  
    <modelVersion>4.0.0</modelVersion>  
  
    <groupId>lk.ijse.dep12</groupId>  
    <artifactId>hello-servlet</artifactId>  
    <version>1.0-SNAPSHOT</version>  
    <name>hello-servlet</name>  
    <packaging>war</packaging>  
  
    <properties>        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>  
        <maven.compiler.target>17</maven.compiler.target>  
        <maven.compiler.source>17</maven.compiler.source>  
        <junit.version>5.10.0</junit.version>  
    </properties>  
    <dependencies>        <dependency>            <groupId>jakarta.servlet</groupId>  
            <artifactId>jakarta.servlet-api</artifactId>  
            <version>6.0.0</version>  
            <scope>provided</scope>  
        </dependency>        <dependency>            <groupId>org.junit.jupiter</groupId>  
            <artifactId>junit-jupiter-api</artifactId>  
            <version>${junit.version}</version>  
            <scope>test</scope>  
        </dependency>        <dependency>            <groupId>org.junit.jupiter</groupId>  
            <artifactId>junit-jupiter-engine</artifactId>  
            <version>${junit.version}</version>  
            <scope>test</scope>  
        </dependency>    </dependencies>  
    <build>        <finalName>${artifactId}</finalName>  
        <plugins>        </plugins>    </build></project>
```

create a directory called `webapp` in src and create the other directory inside it as folllow

![[Pasted image 20240627134121.png]]


|                |                                                                                                                                                                                                         |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what is the DD | DD is the  web.xml file inside the `WEB-INF`. This contains the <br>==deployment description==. Without this file this is not considered<br>as a web application when it is deployed to a web container |
|                |                                                                                                                                                                                                         |
This is how to create the `web.xml` file using the intellij project structure
(set the path correctly)

![[Pasted image 20240627134505.png]]

This is how servlet manipulate reponse and give it to the webserver =>

```Java
package lk.ijse.dep12.ee;  
  
import jakarta.servlet.ServletException;  
import jakarta.servlet.http.HttpServlet;  
import jakarta.servlet.http.HttpServletRequest;  
import jakarta.servlet.http.HttpServletResponse;  
  
import java.io.IOException;  
import java.io.PrintWriter;  
import java.time.LocalDateTime;  
  
public class MyServlet extends HttpServlet {  
  
    @Override  
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {  
        System.out.println("++++++++++++++++++GET Request++++++++++++");  
        System.out.println("==========================================");  
        resp.setContentType("text/html");  
        try (PrintWriter out = resp.getWriter()) {  
            out.println("""  
                    <!DOCTYPE html>                    
                    <html lang="en">                        
                    <head>                            
	                    <title>My First Servlet</title>   
                    </head>                        
                    <body>                            
	                    <h1>Hello World</h1>
	                    <h1>Server Date and Time: %s</h1>
	                </body>                    
                    </html>                    """.formatted(LocalDateTime.now()));  
        }  
    }  
}
```


add image here

what is the purpose of the use of `web.xml` file =>

This is the deployment descriptor. Without this file application sever cannot be find to details to deploy the application. 

The `web.xml` file in servlets configures servlet mappings and declarations for standardized deployment.

```XML
<?xml version="1.0" encoding="UTF-8"?>  
<web-app xmlns="https://jakarta.ee/xml/ns/jakartaee"  
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
         xsi:schemaLocation="https://jakarta.ee/xml/ns/jakartaee https://jakarta.ee/xml/ns/jakartaee/web-app_6_0.xsd"  
         version="6.0">  
	<?servlet declaration?>  
    <servlet>        
	    <servlet-name>ABC</servlet-name>  
	    <servlet-class>lk.ijse.dep12.ee.MyServlet</servlet-class>  
    </servlet>       
     
    <?servlet mapping?>
    <servlet-mapping>  
        <servlet-name>ABC</servlet-name>  
        <url-pattern>/index.html</url-pattern>  
    </servlet-mapping>  
  
</web-app>
```
