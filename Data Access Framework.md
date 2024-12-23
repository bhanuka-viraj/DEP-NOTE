
Note -> Data Access cannot be used stand alone. Need to be worked with the Cor frame work

|                                                                               |                                                                                                                                                                                                                                                                             |
| ----------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the reason <br>to use data access<br>framework                        |                                                                                                                                                                                                                                                                             |
| What is the use of <br>`PgDataSource`                                         | ![[Pasted image 20240901155652.png]]<br><br>this a pool that establish the connection with prostgre sql<br><br>What is the use of those methods -> <br><br>`getConnection()` -> <br>to get the connection to pool<br><br>`close()` -> <br>to release connection (close)<br> |
| What is the reason<br>to use adapter <br>design pattern in <br>`pgDataSource` | The way pool is being handled can be changed with the<br>database management system. Adapter design patter is <br>used to adapt the pool with the any dbms<br><br>                                                                                                          |
|                                                                               | <br>                                                                                                                                                                                                                                                                        |
|                                                                               |                                                                                                                                                                                                                                                                             |
==Q. ==How does the `sessionProxy` is worked when the request are come

![[Pasted image 20240901172746.png]]

==A==. A instance of `CustomerRepositoroyImpl` is not created for each request when use the `data-access` framework. If this framework is not used the request and the instances of each layers are worked as follow.

![[Pasted image 20240901173338.png]]

instances of `ServiceImpl` and `RepositoryImpl` are created for each request and use one instance on controller

With this framework instances of service , repository and request are handled as follow 

![[Pasted image 20240901173919.png]]

Instance of `ServiceImpl` and the `RepopositoryImpl` are not created for the each request. 

Note -> `sessionProxy` is resolve the right database session and the connection for the each methods in the `RepositoryImpl`

