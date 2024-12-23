![[Pasted image 20240617121109.png]]

|                                                                | Forms                                                                                                                                                                                                                                                                                                                                                     |
| -------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what are the<br>type of input                                  | text, radio,check box,input                                                                                                                                                                                                                                                                                                                               |
| what is the default<br>type of input                           | text                                                                                                                                                                                                                                                                                                                                                      |
| what is the default<br>method of form                          | set                                                                                                                                                                                                                                                                                                                                                       |
| what is enctype                                                | The `enctype` attribute in HTML forms specifies how data is encoded (formatted) for submission, ensuring the server interprets it correctly (e.g., `application/x-www-form-urlencoded` (default) for text, `multipart/form-data` for file uploads).                                                                                                       |
| What are the other names<br>that request body is called        | pay load<br>form data                                                                                                                                                                                                                                                                                                                                     |
| what is the difference <br>between `encode` and `encrytpt`     | `encode` -> change the format<br>`encrypt` -><br><br>Encoding transforms data to a another format while encryption secures data by making it unreadable without a key.                                                                                                                                                                                    |
| what is the api<br>`encodeURI`<br>`encodeURIComponent`         | `encodeURI` handles entire URLs, preserving reserved characters like '/' and '?' for proper structure, while `encodeURIComponent` encodes everything for use within a URL component like a query string parameter.<br><br>`encodeURIComponent` has better performance<br>                                                                                 |
| what is URL encoding                                           | URL encoding is converting special characters into a format readable by web browsers so they can understand the URL structure.                                                                                                                                                                                                                            |
| what are the method<br>that can be specified<br>in html `form` | GET -> (url query string)<br>POST ->(request body)<br><br><br>if the method is GET the enctype should be <br>`application / x-www-form-urlencoded`<br><br>if the method is POST the enctype can be either<br>`application / x-www-form-urlencoded `or<br>`multipart / form-data`<br><br>`multipart / form-data`  => This is usually used for file uploads |
| what is `action` in html form                                  | The `action` attribute in an HTML form specifies the URL where the form data is sent for processing when the form is submitted.                                                                                                                                                                                                                           |
| what is `name` in input<br>element                             | The `name` attribute in HTML input elements identifies the data as key-value pairs for server-side processing when a form is submitted.                                                                                                                                                                                                                   |
==This is how html form works==

![[Pasted image 20240617124415.png]]


Explanation ->
![[Pasted image 20240617124122.png]]
Get the name value pairs from the form elements.(if there is a element without a name it is ignored)- This is raw data

Then check the enctype. If the enctype is `application / x-www-form-urlencoded` then name value are encoded format that allowed to embed into a url (This is encoded data)

![[Pasted image 20240617124356.png]]

Then check the method. If the method is GET then it put into a ulr query string. If the method is POST name  values are put in to the request body


![[Pasted image 20240617124633.png]]

then request is sent to the resources that in the `action`

If the enc type is `multi part form data` =>
![[Pasted image 20240617125640.png]]
name value pairs are added to the  request body as parts

https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form

|                                                                      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| -------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what are the <br>specific method<br>for the html input element       | `checked(radio,checkbox):boolean`<br>`disabled:boolean`<br>`value:string`<br>`select():` -> to select the content of the input field<br>`files(file):FileList`<br>`multiple(file):boolean`<br>`accept(file):string(MIME Type)`<br>`checkValidity()` -><br>if all all data are valid then this return the true                                                                                                                                                              |
| how to change the input<br>file type                                 | ![[Pasted image 20240617133204.png]]                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| what are the `submit()` and <br>`reset()` api<br>in form element     | Form element's `submit()` sends data to the server while `reset()` set default values for all values in form element                                                                                                                                                                                                                                                                                                                                                       |
| does `reset` type<br>button clear the <br>values in from element     | It does not clear. It set to the default values                                                                                                                                                                                                                                                                                                                                                                                                                            |
| what are event`submit`<br>and `formdata`<br>of `form`<br>element<br> | both are event for the form element. First trigger the <br>`submit` and then  trigger the `formdata`<br><br>submit -> allow to manipulate  before submission.This can be use for the data validation. This is <br>happen before the submit the form<br><br>formdata ->Data are collected from the this phase<br><br>The `formdata` event in HTML forms provides access to the form's data in its raw format before it's sent to the server, useful for advanced scenarios. |
| how `formdata` <br>works                                             | create a instance from a formdata constructor function and<br>then add the name value pairs to it.This is allowed to add <br>the name value pairs for developers to using the `formdata` method <br>                                                                                                                                                                                                                                                                       |

![[Pasted image 20240617142330.png]]

|                                                                                                       |                                                                                                                                                                                                     |
| ----------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what is the use of<br>`new FormData() `<br>`new FormData(HTMLFormElement)`                            | `new FormData() :formDataInstance` =><br>to create empty formdata instance<br><br>`new FormData(HTMLFormElement)`<br>to create form data instace and add all name values pair from the html element |
| important method <br>in formdata();                                                                   | ![[Pasted image 20240617142510.png]]                                                                                                                                                                |
| what is the <br>`new URLSearchParas(formDataRef)`                                                     | return a  object that form data is encoded to <br>application/x-www-forom-urlencoded<br>                                                                                                            |
| what is the difference between<br><br>`new FormData() ` and <br>`new URLSearchParas(formDataRef)`<br> | `new FormData()` for encoding type multi part form data<br><br>`new URLSearchParas(formDataRef)` <br>encoding type <br>for `application/x-www-form-urlencoded`<br>                                  |

`Both have this methods`

![[Pasted image 20240617143522.png]]

how form  works during submit and formdata  -> Explain one by one 

![[Pasted image 20240617231942.png]]

==what are the main mime type for data encode and their objects==

1.Application/x-www-form-urlencoded => `URLSearhcParam`
2.multipart/form-data =>`FormData`
3.application/json => `Json`

what are the main api of Json =>
JSON.stringfy(JavaScriptObject) => String
JSON.parse("String") => JavaScriptObject

|                                                                        |                                                                    |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------ |
| what are the <br>draw back of html forms                               | does not support JSON<br>only support for GET and POST methods<br> |
| what are the other ways <br>that allow js to connect <br>with back end | XHR/ Fetch                                                         |
