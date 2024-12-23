
|                                                                                          |                                                                                                           |
| ---------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| When servlet context<br>is cretaed                                                       | Just after create the logical deployment descriptor<br><br>In this time servlet context is empty          |
| Where servlet context<br>(empty servlet context)<br>details get from                     | Data are taken from the logical deployment descriptor<br>and register them in the servlet context<br><br> |
| What is the order that<br>servlet context register<br>serlvet, filtsers and <br>listners | 1. Listners<br>2. Filters<br>3. Servlets                                                                  |
![[Pasted image 20240701162604.png]]

Note -> Listeners and filters are registered first. Then Servlets are registered next according to the `loadOnStartup` value. Main purpose to load the servlet is register them in the servlet context.
[[How servlets are loaded]] This is happen because servlet context is needed to register it.

Main purpose of loading servlets object is register them in the serlvet context