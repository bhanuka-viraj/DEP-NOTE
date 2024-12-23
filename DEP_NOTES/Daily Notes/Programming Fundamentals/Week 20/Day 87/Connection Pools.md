|                                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| -------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what is the reason<br>to use connection pool | This is used to give the connection from database not <br>giving direct connection from the database. When <br>using connection pool it is connected with the data <br>base and developer are allowed to connect with the<br>connection pool. (usually developer do not get the direct<br>access to the database)<br><br>And also if connected with the directly data base it is <br>only allowed to connect to a one user. When using <br>connection pool multiple users can be connected. And<br>also connection pool are production level and amount<br>of the connection in the connection pool is shrinked<br>and grew as necessary. (similar to the threads in thread pools)<br><br><br>If user directly connected with the database user have to<br>establish the connection between database every <br>time. But when use a connection pool it is already <br>connected with the data base and then users are <br>connected with the connection pool. This enhance performance of the application |
| What is datasource                           | In java this is used to represent the connection pool<br><br>![[Pasted image 20240704123444.png]]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
![[Pasted image 20240704115608.png]]


[[How to create connection pools]]

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |     |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| How to connect the app with connection pools. This might changed with the application server <br><br>in tomcat -> <br>`use annotation` -><br>`@Resource(lookup = "java:comp/env/jdbc/to-do-app-db")`<br><br>![[Pasted image 20240704214508.png]]<br><br>in glassFish -><br>`use annotation` -><br>`@Resource(lookup = "jdbc/to-do-app-db")`<br><br><br>`jdbc/to-do-app-db` is the connection pool name in here.<br>It should be changed with the necessary pool name<br><br><br>creating connection pools is not a part of the developers. Usually developers get the pool name to connect with the connection pool<br> |     |
```java
package lk.ijse.dep12;  
  
import jakarta.annotation.Resource;  
import jakarta.servlet.ServletException;  
import jakarta.servlet.annotation.WebServlet;  
import jakarta.servlet.http.HttpServlet;  
import jakarta.servlet.http.HttpServletRequest;  
import jakarta.servlet.http.HttpServletResponse;  
  
import javax.naming.InitialContext;  
import javax.naming.NamingException;  
import javax.sql.DataSource;  
import java.io.IOException;  
import java.sql.Connection;  
import java.sql.SQLException;  
  
@WebServlet(name = "my-servlet", urlPatterns = "/hello" ,loadOnStartup = 0)  
public class MyServlet extends HttpServlet {  
  
    @Resource(lookup = "java:comp/env/jdbc/to-do-app-db") // this is for tomcat  
   /* @Resource(lookup = "jdbc/to-do-app-db") */// this is for glass fish    private DataSource dataSource;  
  
    @Override  
    public void init() throws ServletException {  
        System.out.println("Init:"+dataSource);  
    }  
  
    @Override  
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {  
        try {  
            Connection connection = dataSource.getConnection();  
            resp.getWriter().printf("<h1> New Connection: %s</h1>", connection);  
            connection.close();  
        } catch (SQLException e) {  
            resp.getWriter().printf("<h1>Failed to obtain a connection, Reason: %s</h1>  " , e.getMessage());  
            e.printStackTrace();  
        }  
  
    }  
}
```
