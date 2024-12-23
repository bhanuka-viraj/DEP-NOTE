
syntax =>

![[Pasted image 20240619192819.png]]

```js
btnFetchWrite.addEventListener('click', async () => {  
    const response = await fetch('https://jsonplaceholder.typicode.com/todos',  
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
        });  
  
    console.log(await response.json());  
  
});
```

What are the content type of the header that is set default according to their body =>

| mime type       | Content Type of header              |
| --------------- | ----------------------------------- |
| From Data       | `multipart/form-data`               |
| URLSearchParams | `application/x-www-form-urlencoded` |
| String / Json   | text / plain                        |
|                 |                                     |

When use the Json the content type of the header usded be set as the `application/Json`. Because it is set default as text/plain