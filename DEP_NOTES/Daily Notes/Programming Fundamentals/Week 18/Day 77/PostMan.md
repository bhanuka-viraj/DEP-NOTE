
|                                                              |                                                                                                                           |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------- |
| what is postman                                              | HTTP client                                                                                                               |
| Does postman has<br>two difference engine <br>like browser   | Earlier,postman didn't have a rendering engine. Now <br>it has a rendering engine for basic preview                       |
| What is the purpose <br>of using postman                     | -> HttpClient (with a rendering engine)<br>->Mock Server<br>-> Documentation Generation Tool<br>-> To test websockets<br> |
| What are the <br>variables in postman                        | Global Variables<br>Env. Variables<br>Collection Variables<br>local variables                                             |
| Global Variables                                             | Global variables can be used within any where in collection.<br><br>But cannot be used with mock servers                  |
| Environment Variables                                        | Environment can be connected to the  collection. Then<br>variables of environment can be used.                            |
| what are the uses <br>of collections in postman              | organize request<br>create mock Servers<br>generate Documentation (api documentation)<br>                                 |
| Collection variabels                                         | Variables that valid within collection                                                                                    |
| local variables                                              | variables within the request response life cycle                                                                          |
| what are the variables<br>that can be used with mock servers | Environment variables and collection variables                                                                            |


|                                                          |                                                                                                                                                                                                                                                                                                                             |
| -------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what is the path segment of a url                        | A URL's path segment is a **part of the address separated by forward slashes (`/`)**. It helps specify the location of a resource within the website's hierarchy.<br><br>For example, in the URL `https://www.example.com/products/clothing/shirts`, "products", "clothing", and "shirts" are all individual path segments. |
| what are the path<br>variables                           | Path variables in URLs are placeholders that represent dynamic segments within the path, allowing you to target specific resources.<br><br>When the path segment is dynamically changed                                                                                                                                     |
| how to set path <br>variables to the url                 | add `:` to the url                                                                                                                                                                                                                                                                                                          |
| what is the `example` in postmam                         | ![[Pasted image 20240618192407.png]]<br><br>example is a static response                                                                                                                                                                                                                                                    |
| what is the best tool for static <br>response generation | Postman                                                                                                                                                                                                                                                                                                                     |
| What is the <br>best tool for<br>dynamic response        | Not the postman. use mockoon instead                                                                                                                                                                                                                                                                                        |
 Path variables -> 
 
 Path variables in URLs are like wildcards within path segments, typically denoted by a colon (`:`). They act as placeholders that can be replaced with specific values to target dynamic resources within the website's structure.

Imagine a path segment like "users" in a URL. A path variable could be something like "users/:id" where ":id" represents a variable segment. This allows you to create URLs like "users/123" or "users/john_doe" to target specific user profiles based on the value filled in for ":id".
![[Pasted image 20240619004132.png]]

|                                    | Tabs of Request                                                                                                                                   |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| Header Tab in request              | To set the header                                                                                                                                 |
| body Tab in request                | To set the payload                                                                                                                                |
| Authorization                      | To set the credential                                                                                                                             |
| Params                             | to set the path variables and query parameters                                                                                                    |
| Pre-request Script                 | The is executed before the send the request.<br>This allow to manipulate the request before it send                                               |
| Test<br>Post-request Script        | This is executed after receive the response<br>This allow to manipulate the response                                                              |
| Collection Pre-Request<br>Script   | This is executed before all request within collection<br>(this is situated in collection)<br><br>not allowed to changed the body of the response  |
| Collection Post  Request<br>Scirpt | This is executed before all response within collection<br>(this is situated in collection)<br><br>not allowed to changed the body of the response |
This is the response request life cycle
![[Pasted image 20240619004103.png]]

Below diagram describe how does the request response life cycle works with two request (this same for the the multiple request) when the postman is the HTTP client (when used for the back end testing) =>


![[Pasted image 20240618175250.png]]

Below diagram describe how does the postman as a mock server. (when used for the front end testing)
![[Pasted image 20240618175536.png]]


[[Environments in Postman]]

reference for the postman with js =>
https://learning.postman.com/docs/tests-and-scripts/write-scripts/postman-sandbox-api-reference/