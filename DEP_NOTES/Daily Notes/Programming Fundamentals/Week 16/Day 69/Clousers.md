
|                            |                                                                                                                                                                                 |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what are the <br>clouseres | In JavaScript, closures are functions that can access variables <br>from their outer function's scope (lexical scope) even after the outer function has finished executing.<br> |
```js
let i = 5;  
  
function OuterFn(x,y){  
    let sum = x + y; // 30  
  
    function innerFn(value){  
        let total = value + sum;  
        sum = total + i;  
        i = sum;  
        return total;  
    }  
    return innerFn;  
}  
  
const result = OuterFn(10,20)(30);  
console.log(`result=${result}, i=${i}`)  
/*result=60, i=65*/
```

==when a function is executed , function environment is created==
![[Pasted image 20240607032221.png]]

![[Pasted image 20240607032243.png]]

![[Pasted image 20240607032305.png]]