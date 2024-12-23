
==What is the difference between `fetch` and `axios` in `GET` methods =>==

1.Fetch response is required to convert to the js object and axios response is not required to convert


```js
btnGET.addEventListener('click', async (e) => {  
  
    const response1 = await fetch(URL);  
    console.log(response1.json());  
  
    const response = await axios(URL);  
    console.log(response.data);  
});
```

==what is the difference between `fetch` and `axios` in `SET` methods =>==

```js
btnSET.addEventListener('click', async (e) => {  
    const responseBody = await (await fetch(URL, {  
        method: 'POST',  
        body: JSON.stringify({  
            userID: 1,  
            title: "New Task",  
            completed: false,  
        }),  
        headers: {  
            'Accept': 'application/json',  
        }  
    })).json();  
    console.log("FETCH RESPONSE BODY", responseBody)  
  
    const responseBody1 = await axios(URL, {  
        method: "SET",  
        data: {  
            userID: 1,  
            title: "New Task",  
            completed: false,  
        },  
        headers: {  
            "Content-Type": "application/json"  
        }  
    });  
    console.log("AXIOS RESPONSE BODY: ", responseBody);  
});
```

1.Fetch need to get a json object as a body and axions can get a js object and convert it to json by itself

==How to set intercept using axios for request and response =>==

```js
axios.interceptors.request.use((config) => {  
    console.log("Now we can intercept the request before it sends to the server");  
    console.log("REQUEST:", config);  
    return config;  
});  
  
axios.interceptors.response.use((config) => {  
    console.log("Now we can intercept the response before it retrieves to the client");  
    console.log("RESPONSE:", config);  
    return config;  
})
```

add -> github link here