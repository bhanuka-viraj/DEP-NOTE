This is the priority order => 

1.Servlet Mapping
2.Welcome file list (web.xml)
3.index.html
4.index.jsp


Just imagine the request URL = `locahost:8080/app/ijse`

when get the request first find is there a servlet with a url pattern of `/ijse`. If it exist then resolve the servlet. If there is no servlet with the url pattern then create a ==partial valid request== putting a forward slash at the end.

partial valid request - > `localhost:8080/app/ijse/`

Now check the welcome list. If there is no defined welcome list there are two default welcome list called `index.html` and `index.jsp`. Now check is there a static resource in `app/ijse/index.html`. If this not exist then check is there a static resource in `app/ijse.index.jsp`. If these are exist then resolve them. If those are not exist then check is there are servlet with a URL pattern that matched with `/ijse/index.html`. If it is not exist then go for the servlet `/ijse/index.jsp`. If both servlet are not exist then go for the default servlet. If a default servlet is not defined then return a 404 error.

If there are defined welcome pages above scene is replaced with those files names

above explanation in servlet specification => 

link -> https://jakarta.ee/specifications/servlet/6.0/jakarta-servlet-spec-6.0#welcome-files

![[Pasted image 20240702175312.png]]

