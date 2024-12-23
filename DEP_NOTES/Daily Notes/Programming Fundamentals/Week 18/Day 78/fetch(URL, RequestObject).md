```js
const request= new Request(`https://jsonplaceholder.typicode.com/todos`,  
    {  
        method: 'POST',  
        body: JSON.stringify({  
            userId: 1,  
            tittle: "New To-Do item",  
            completed: false  
        }),  
  
        headers:{  
            'Content-Type': 'application/json'  
        }  
})  
  
btnFetchWrite.addEventListener('click', async () => {  
    const response = await fetch(request)  
  
    console.log(await response.json());  
  
});
```
