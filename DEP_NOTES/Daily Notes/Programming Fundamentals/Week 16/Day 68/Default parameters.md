How default parameters is worked 

![[Pasted image 20240605125109.png]]

In this function if the address in not defined or defined as `undefined` then default value is taken as the parameter. If the parameter is null, then parameter is taken as the null. 

To deal with the null values, `Nullish Coaslecing` is the better way 

![[Pasted image 20240605125403.png]]

Refer this ->

![[Pasted image 20240605130456.png]]

Default variable can be a expression, also even can be a left side parameter of the function

```Js
printCustomer("C001","Kasun" ,null);  
  
function myFn(x = 10,y,k = x + y) {  
    console.log(x, y, k);  
}  
  
myFn(undefined ,20); // x = 10, y = 20,30
```

Explain this example ->

```Js
function myFn2(x = arguments[2], y = arguments[0], k = 30) {  
    console.log(x, y, k);  
}  
  
myFn2(undefined, 20, 50);  
/*50 20 50*/
```

![[Pasted image 20240605131702.png]]

Explain this example ->

```Js
function myFn2(x = arguments[3] ?? 30, y = x, k = x + y) {  
    console.log(x, y ? 70 : 50, k);  
}  
  
myFn2(undefined ,[],undefined,null);

// 30 70 30
```


