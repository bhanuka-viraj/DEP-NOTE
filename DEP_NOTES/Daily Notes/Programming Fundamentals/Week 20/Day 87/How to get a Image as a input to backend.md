![[Pasted image 20240704175116.png]]

Back ends does not support `mulitpart form data` in default. First of all multi part configuration should be done.

This annotation is used to config the servlet with the multi part form data
`@MultipartConfig(location = "/temp", maxFilSize = "5 x 1024 x 1024"`

|                                             | `@MultipartConfig(location = "/temp", maxFilSize = "5 x 1024 x 1024"`                                                                                                                                                                                                                                                                                                                          |
| ------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the location                        | In multipart form data names and values are stored in a part <br>structured in to a header and body.(key in the  header and the value in the body)<br><br>When a file is send in a request it is loading top to bottom. So <br>file is required to store temporally. `Location` is the location <br>where it is stored temporally.<br><br>Usually `/temp` is the directory that is used for it |
| What is the <br>max file size               | This is used to set the maximum size of the file                                                                                                                                                                                                                                                                                                                                               |
| what is the <br>method <br>`getParameter()` | The `getParameter(String name)` method in the `HttpServletRequest` interface is used to retrieve the value of a request parameter sent by the client (such as a form field). This method returns the value of the specified request parameter as a `String`, or `null` if the parameter does not exist.                                                                                        |
| what is the <br>method `getPart()`          | this method return a part of a `multi part form data`                                                                                                                                                                                                                                                                                                                                          |

[[How does the `getParameter()` work]]

getPart()
wirte()


```Java
protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {  
    String name = req.getParameter("name");  
    String email = req.getParameter("email");  
    String password = req.getParameter("password");  
    System.out.printf("name=%s, email=%s, password=%s \n",name, email, password);  
    Part picture = req.getPart("picture");  
  
    try(Connection connection = pool.getConnection()) {  
        PreparedStatement stm = connection.prepareStatement("""  
                                INSERT INTO "user" (email,password,name,picture) VALUES (?,?,?,?)  
                """, Statement.RETURN_GENERATED_KEYS);  
        stm.setString(1,email);  
        stm.setString(2,password);  
        stm.setString(3,name);  
        stm.setBinaryStream(4,picture.getInputStream());  
        stm.executeUpdate();  
        ResultSet rs = stm.getGeneratedKeys();  
        rs.next();  
        int newUserId = rs.getInt("id");  
        resp.setStatus(HttpServletResponse.SC_CREATED);/*Status code should be added before body*/  
        resp.setContentType("application/json");  
        resp.getWriter().print("""  
                {                "id":%s,                "email":"%s",                "name":"%s",                }                """.formatted(newUserId,email,name));  
        resp.getWriter().flush();  
    } catch (SQLException e) {  
        resp.getWriter().printf("<h1>Failed to save the user: $s</h1>".formatted(e.getMessage()));  
        e.printStackTrace();  
    }  
  
}
```
\