![[Pasted image 20240530160713.png]]


```Js
function executor(resolve, reject) {
    setTimeout(function () {
        resolve("Hi....!")
    }, 5000);
}

/*wrapping in a promise*/
let promiseRef = new Promise(executor);
console.log(promiseRef);
console.log("Come here"); 

/*checking status after 10 seconds*/
setTimeout(function () {
    console.log(promiseRef);
}, 10000);
```
