How to send a get request =>

```js
const API_URL = "https://jsonplaceholder.typicode.com/todos";  
  
const response1 = await axios(API_URL);  
console.log(response1.data);
```

How to send a post request =>
```js
const response2 = await axios(API_URL,{  
    method:'POST',  
    data:{  
        userID:1,  
        title: 'New Task',  
        completed:false,  
    },  
    headers:{"content-type":"application/json"},  
});  
  
console.log(response2.data);
```
