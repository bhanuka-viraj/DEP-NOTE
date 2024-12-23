
XHR - XMLHttpRequest

Below steps are 

#### STEP 1 -> Create the XHR instance
`const xhr = new XMLHttpRequest();`
#### STEP 2-> Create a call Back function

```Js
xhr.addEventListener('readystatechange', (event) => {  
  
});
```
Q.What is the reason to create call back function
A. Call back function is exuecuted when got the response. Don't know when the response is come. This is why callback function is used
#### STEP 3 -> Open the request

`xhr.open('GET', https://ijse.lk, true);`

add user name and password at the end of the `open( )` method if it requires the username and password of the data base fire wall

What does mean open -> 

==Initiate the connection between client and server==

Open the socket. Now server and client has connected. The call back function is executed for the first time

#### STEP 4 -> Set Additional Data

Append additional headers and prepare payload
#### STEP 5 -> Send the Request

`xhr.send( )`
#### ==Ready State==

|                             |                                                                                                                                                                                          |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the <br>ready state | An XHR's `readyState` property is a single number indicating the current stage of an asynchronous request, helping you determine when the data is ready for use in your JavaScript code. |
![[Pasted image 20240617174617.png]]
(3) => Response body hold partial data

|                                                   |                                                                                             |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| How many time <br>call back function<br>is called | 4 times. <br>one time before receive the response><br>Three time after receive the response |
| How to access<br>headers in response              | `xhr.getResponseHeaders(Header name):String`<br>`xhr.getAllResoponseHeaders([data])`<br>    |
| when allow to access<br>headers                   | when the ready state pass the value 2                                                       |

What is the api to read the response body ->
![[Pasted image 20240617181632.png]]

#### Load Events
```js
btnGetAllEmployee2Elm.addEventListener('click', () => {  
  
    const xhr = new XMLHttpRequest();  
    xhr.addEventListener('readystatechange', () => {  
        if(xhr.readyState === XMLHttpRequest.DONE && xhr.status === 200) {  
  
            console.log(xhr.responseText);  
        }  
    });  
  
    xhr.addEventListener('loadstart', () => {  
        console.log("Loadstart")  
    });  
  
    xhr.addEventListener('loadend', () => {  
        console.log("Load end")  
    });  
  
    xhr.addEventListener('load', () => {  
        console.log("Load")  
    });  
  
    xhr.addEventListener('readystatechange', () => {  
        console.log("readystatechange", xhr.readyState);  
    });  
  
    xhr.open('GET', `${API_URL}/employees`,false);  
    //async only apply for the send() method. Even open() it self is 
    //not a asycn function.
    console.log('open');  
  
    xhr.send();  
    console.log('send');  
  
});
```

|                                                        |                                                                                                                                                                                  |
| ------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what are the other events                              | `loadstart`<br>`loadEnd`<br>`load`                                                                                                                                               |
| when `loadStart` event is triggered                    | when the header is started to load<br><br>this is not working when the async is false                                                                                            |
| when `load` is triggered                               | after loading the response completely (after state code 4)                                                                                                                       |
| when  `laodEnd` is trigerred                           | after loading the response completely (after state code 4)                                                                                                                       |
| what is the difference between<br>`load` and `laodEnd` | both `load` and `loadEnd` are trigerred if response comes. Not depend on the response code.<br><br>`load` is not triggered if the response not come.<br>(like a network failure) 

When async is true =>

![[Pasted image 20240618200652.png]]
explain above output ss => what is the reason to loadstart appeared before the 
send (because console.log also a async function);

As  the thoery `send` should be printed before the `loadstart`. But it is not happen because both are async

when async is false =>

![[Pasted image 20240618201855.png]]

async in the `open( )` method is only applied for the `save ( )` method. Even it is not applied for the open itself.  So `open( )` method is executed as a sync function. Then `readystatechange` and `open` are printed first. Since `send( )` is a async function in here, all `Load start`, `send` , `Ready stae 2`, `Ready state 3` ,

==`async` only apply for the `send( )`==
![[Pasted image 20240618204501.png]]



[[How to send POST request using XHR]]