
|                                                   |                                                                                                                                                                                                                |
| ------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what is the main objective<br>of MVC architecture | separating model from the view. If the model is <br>isolated then it can be used another view later. <br>And also easy to change the UI later.<br><br>The controller is used to connect the model and view<br> |
| What MVC stand for                                | Model View Controller <br><br>Model -> data and logic (database)<br><br>controller -> to control the view. Controller and <br>view is coupled. <br>                                                            |
## original MVC pattern -> 

Controller coupled with the view. Controller give the changed of the view to model. Model is subscribed by the view. Then view will notify the changes of the model

![[Pasted image 20240815133515.png]]


## Model - View - presenter (this is derived from the MVC)

MVC was used for the desktop application. MVC was changed when it comes to use with the web application. 

==Q.== What is the reason to change the MVC for web applications.
==A.== View is in the client side in web application. Since the model is notify the changes to the view, the server side has to send the request to the client. This does not fit with the HTTP protocol. This is why MVP was derived from the MVC for web application that are used client-server architecture. 

Q. How does the MVP Works -> 
A. Presenter keep the connection between both view and the model in bidirectionally

![[Pasted image 20240815134359.png]]



==Q.==What is the Model-View-View-Model

==A.== In here presenter and the View is binded. Binder frame work like react and angular used this architecture

|                                          |                   |
| ---------------------------------------- | ----------------- |
| What is the front end part<br>of the MVP | Presenter - View  |
| What is the backend part<br>of the MVP   | Presenter - Model |
|                                          |                   |

## MVC - 2 (MVC extended architectural pattern) / Layered Architecture / N-tier Architecture

In here mode is divided in to two part.
1. Database
2. Business Logic

![[Pasted image 20240815135255.png]]

This also can be show like layers. To do this should be a MVP instead of MVC.Because MVC has the connection between model and the view. Then this layer system cannot be show. This is should be a MVP rather MVC


To keep the web services (api) in the model another layer is added called api layer

![[Pasted image 20240815140913.png]]

![[Pasted image 20240815141027.png]]

|                                                                                   |                                                                                                                                                                                                                                                                                                                              |
| --------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the purpose of <br>the api layer                                          | To expose the web services <br><br>When web services are restfull web servies, the api <br>layer is called Rest-Controller<br><br>                                                                                                                                                                                           |
| What is the difference <br>between bussiness <br>layer and the services <br>layer | Both denote the same layer.                                                                                                                                                                                                                                                                                                  |
| What is the difference <br>between DAO and the <br>Repository                     | Both denote the same layer (Data Access). <br>DAO was used previously and now it called as <br>repository                                                                                                                                                                                                                    |
| What does mean the <br>layer is closed                                            | Not allowed to byapass a layer from another layer. <br>In default all layers are closed                                                                                                                                                                                                                                      |
| How to denote the <br>close layers                                                | `X`                                                                                                                                                                                                                                                                                                                          |
| Is it allowed to open<br>layers                                                   | Yes. Architecture some time  have open layers. It should be <br>defined what is the reason to open it. Usually layers <br>makes open for enhance the performance                                                                                                                                                             |
| What is the standard<br>amount of layers in model                                 | betst 3 -5<br>max - 7<br><br>This is the amount of the layers in the model<br>                                                                                                                                                                                                                                               |
| What is the monolithic<br>architecture                                            | **Monolithic architecture** in the context of **layered architecture** refers to a traditional software design approach where the entire application is built as a single, unified unit or codebase<br><br>What is the disadvantage of monolothic -> <br>have to down the whole app in maintenance of a <br>single layer<br> |

Monolithic -> 

**Monolithic architecture** refers to a software design pattern where all components of an application are tightly integrated and operate as a single unit. In this architecture, different modules or functionalities of an application (like the user interface, business logic, and data access layer) are built as one unified codebase and deployed together.

Monolithic architecture is often suitable for smaller applications, startups, or projects where simplicity and quick deployment are more critical than scalability and flexibility. However, as the application grows, it may be necessary to consider migrating to a more modular or microservices architecture to address the limitations of a monolithic system.

==What are the responsibilities of those layers -> ==

![[Pasted image 20240815211328.png]]

|                        |                                                                              |
| ---------------------- | ---------------------------------------------------------------------------- |
| API \| REST controller | To Expose web services(main responsibility)<br>DATA validation               |
| Business \| Service    | Business Validation<br>Business Logics<br>Transactions <br>Data base session |
| DAO \| Repository      | Data                                                                         |

|                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| -------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What are the ==cross <br>cutting concerns==              | Same thing that we could found in the several layer<br>(see below for the detailed explanation)<br>Examples -> <br><br>->security<br>->login<br>->Exception and error handling<br>                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| What does mean the<br>aspects                            | **aspect** of a program is a [feature](https://en.wikipedia.org/wiki/Software_feature "Software feature") linked to many other parts of the program, but is not related to the program's primary function. An aspect [crosscuts](https://en.wikipedia.org/wiki/Cross-cutting_concern "Cross-cutting concern") the program's core concerns, therefore violating its [separation of concerns](https://en.wikipedia.org/wiki/Separation_of_concerns "Separation of concerns") that tries to encapsulate unrelated functions.<br><br>some aspects are found in the several layers. Those are called <br>cross cutting concerns |
| what is the aspect oriented programming paradigm         | a programming paradigm designed to improve and increase modularity by enabling the separation of cross-cutting concerns.<br><br>-> When use the aspect oriented programming the cohesion is improved of the project                                                                                                                                                                                                                                                                                                                                                                                                        |
| What is the to / DTO                                     | These are used to transfer data between layers                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| What is the purpose of using <br>converters              | These are used to convert the json to dto or dto to json                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| What are the <br>entity object                           | These are used to transfer data between  business layer <br>and Repository layer / Dao                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| What does mean <br>a standard project                    | If the cohesion is high and the coupling is low, then this <br>projects are called standard project                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| What is the <br>Single Responsibility principle<br>(SRP) | Give a single responsible for the component as much as possible                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| [[Design Principles]]                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |


## Micro Services

![[Pasted image 20240815142725.png]]

In Here Model part is divided in to difference services.

**microservice architecture** is a software design pattern where an application is developed as a collection of small, loosely coupled, and independently deployable services. Each service in a microservice architecture corresponds to a specific business functionality and can operate, develop, and scale independently of other services.

|                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is service <br>orchestrate  | process of managing and coordinating multiple microservices to execute a specific business process or workflow                                                                                                                                                                                                                                                                                                                                                                                        |
| What is load balancer            | distributes incoming network traffic across multiple backend services or servers to ensure no single service is overwhelmed.                                                                                                                                                                                                                                                                                                                                                                          |
| What is the service<br>discovery | process that enables microservices to automatically detect and communicate with each other.                                                                                                                                                                                                                                                                                                                                                                                                           |
| circuit breacker                 | To identify the downed services and up them                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| What is spring<br>cloud          | Spring Cloud focuses on providing good out of box experience for typical use cases and extensibility mechanism to cover others.<br><br>- Distributed/versioned configuration<br>    <br>- Service registration and discovery<br>    <br>- Routing<br>    <br>- Service-to-service calls<br>    <br>- Load balancing<br>    <br>- Circuit Breakers<br>    <br>- Distributed messaging<br>    <br>- Short lived microservices (tasks)<br>    <br>- Consumer-driven and producer-driven contract testing |
|                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

