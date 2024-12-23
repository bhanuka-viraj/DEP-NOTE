![[Pasted image 20240619190043.png]]

using then => catch => finally
```js
btnFetchReadElm.addEventListener('click', () => {  
    fetch(`${API_URL}/employees`).then(value => {  
        console.log(value);  
    }).catch(err => console.log(err))  
        .finally(() => console.log("newa gilunath ban choon"));  
});
```


Using try-catch-block

```js
btnFetchReadElm.addEventListener('click', async () => {  
  try{  
        const response =await fetch(`${API_URL}/employeesbfddfb`);  
        console.log(response);  
    }catch(e){  
        console.log(e);  
    }finally {  
        console.log("Nawa gilunath ban chun");  
    }  
  
});
```