refer this link for HTTP method -> 
https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET

What are the method in a HTTP request

GET, POST, TRACE, PATCH, DELETE, PUT, OPTIONS, HEAD

==complete this body==

|                                | GET | POST   | PUT     | PATCH   | DELETE  | HEAD | OPTIONS |
| ------------------------------ | --- | ------ | ------- | ------- | ------- | ---- | ------- |
| REQUEST <br>BODY               | No  | Yes    | Yes     | Yes     | May be* | No   | No      |
| RESPONSE<br>BODY               | Yes | Yes    | May be  | May be  | May be* | No   | May be* |
| Successful<br>Response<br>Code | 200 | 201    | 201/204 | 204/200 | 204/200 | 200  | 200     |
| READ-ONLY                      | Yes | No     | No      | No      | No      | Yes  | Yes     |
| SAFE                           | Yes | No     | No      | No      | No      | Yes  | Yes     |
| Idempotent                     | Yes | No     | Yes     | No      | Yes     | Yes  | Yes     |
| Cacheable                      | Yes | May be | No      | May be  | May be  | Yes  | No      |

|                                                             |                                                                                                                                                                                                                                                                                        |
| ----------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What does `safe`<br>means in HTTP                           | An HTTP method is **safe** if it doesn't alter the state of the server. In other words, a method is safe if it leads to a read-only operation.<br><br>All safe methods are idempotent , but not all idempotent are safe.For example `PUT` and `DELETE` are both idempotent but unsafe. |
| What does mean<br>idempotent                                | one where the effect of making a single request is <br>the same as the effect of making multiple identical requests<br><br>==method like `PUT`, `DELETE`,`PATCH`  are totally depend<br>on developer whether it is idempotent or not==                                                 |
| What does mean<br>cacheable                                 | The HTTP cache stores a response associated with a <br>request and reuses the stored response for subsequent requests.                                                                                                                                                                 |
| What is the use of `GET`                                    | To get the pointed resource                                                                                                                                                                                                                                                            |
| What is the use of <br>``POST``                             | To create<br>To save the body on the request in the pointed <br>resource                                                                                                                                                                                                               |
| What is the use of <br>``PUT``                              | To create if the resource is not there,<br>To replace if the resource is there.<br>(This is not used to update. don't tell this in interview)                                                                                                                                          |
| What is the use of <br>`PATCH`                              | To update resource                                                                                                                                                                                                                                                                     |
| What is the use of <br>`DELTE`                              | To delete the resources<br>                                                                                                                                                                                                                                                            |
| What is the use of <br>`HEAD`                               | To only get the  head of the response                                                                                                                                                                                                                                                  |
| What is the use of<br>`OPTIONS`                             | To get the options(http method) that support from the <br>servers. This happen when the connect with two servers                                                                                                                                                                       |
| What is the meaning <br>of this response<br>successful code | `200` -> ok<br>`201` -> created<br>`204`-> No content                                                                                                                                                                                                                                  |
| Is it allowed to use <br>a body in the <br>`DELETE` request | It is not allowed do in previous. But Now can be have a <br>body in the DELETE .But Usually don't use<br><br>MAY                                                                                                                                                                       |

Example for `POST` Request ->

```HTTP
POST /test HTTP/1.1
Host: foo.example
Content-Type: application/x-www-form-urlencoded
Content-Length: 27

field1=value1&field2=value2

```

Example for `PATCH`
```HTTP
PATCH /file.txt HTTP/1.1
Host: www.example.com
Content-Type: application/example
If-Match: "e0023aa4e"
Content-Length: 100

[description of changes]

```

Example for `PUT`

```HTTP
PUT /new.html HTTP/1.1
Host: example.com
Content-type: text/html
Content-length: 16

<p>New File</p>

```
