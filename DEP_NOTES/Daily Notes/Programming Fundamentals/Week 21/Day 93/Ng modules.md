|                                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what is ng modules                       | Angular modules. It organize the user interfaces and <br>required resources <br><br>components <br>pipes<br>Services<br>Guards<br>Interception<br><br>When angular module is created a injection module is set<br><br>A compliation unit is created -><br>Modules can be configured for lazy loading. This means they are loaded on demand only when the user navigates to a specific feature area, improving initial load time and overall application performance. <br><br> |
| are ng modules same<br>as the js modules | They are not equal. But any NgModule is a js modules                                                                                                                                                                                                                                                                                                                                                                                                                          |
| What is import                           | To import ng module                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| What is providers                        | This is a context. Can be added singleton instances.                                                                                                                                                                                                                                                                                                                                                                                                                          |
| What is bootsrap                         | when bootstrap the module                                                                                                                                                                                                                                                                                                                                                                                                                                                     |


app.module.ts -> This is the root module of the application

![[Pasted image 20240711211129.png]]

 

|              |                                                                                                                                                                                                                                     |
| ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| declarations | The components that belongs to the angular module                                                                                                                                                                                   |
| imports      | Imported angular modules to this angular modules                                                                                                                                                                                    |
| providers    | This create a context within the angular module and also<br>create a injection at the same time.Can be added singleton<br>of the declared components. The added component is accessed <br>among the other components of the module. |
| bootsrap     | the component that is going to started by this module                                                                                                                                                                               |


![[Pasted image 20240712124950.png]]


documentation -> https://angular.dev/guide/ngmodules

