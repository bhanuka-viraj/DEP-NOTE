
In `tomcat`  =>

link for  How to create JNDI Datasource ->
https://tomcat.apache.org/tomcat-8.0-doc/jndi-datasource-examples-howto.html

copy postgresql jar file to tomcat home lib

![[Pasted image 20240704215412.png]]

add this part to bottom of the context.xml file and save ->

![[Pasted image 20240704215535.png]]

![[Pasted image 20240704215637.png]]


```
 <Resource name="jdbc/to-do-app-db" auth="Container"
          type="javax.sql.DataSource" driverClassName="org.postgresql.Driver"
          url="jdbc:postgresql://127.0.0.1:12500/dep12_to_do_app_db"
          username="postgres" password="yasith12345" maxTotal="20" maxIdle="10" maxWaitMillis="-1"/>
```
This is take from the above link

in `glassFish` =>

Refer Yasith's note -> https://www.notion.so/ToDo-App-e17b0368144a4ba0951a0cbf73f8c79f

