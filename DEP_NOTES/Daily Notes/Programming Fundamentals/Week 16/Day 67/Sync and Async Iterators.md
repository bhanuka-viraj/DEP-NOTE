
|                                                                         |                                                                                                                                                                             |
| ----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What are the two <br>iterator types in Java Script                      | `Sync Iterators` -><br>examples -><br>`for..of`<br>`for..await..of`<br><br>`Async Iterators` -><br>examples -><br>`for...await..of`                                         |
| What is the difference between<br>`sync iterators` and `async iterator` | Sync iterators give the answer immediately<br>while Async iterators give the answer taking some time                                                                        |
| what are the other <br>variations<br>of `for..of` and `for..await..of`  | `for..of[await promiseRef]`<br>square bracket part should be a sync iterator<br><br>`for..await..of [await promiseRef]`<br>square bracket part could be either syn or async |

![[Pasted image 20240604140727.png]]

how to use `for...of[await promiseRef]` ->

values come without any delay , but iterator comes with a delay

```Js
const employee = {  
    id: "E001",  
    name: "Kasun Sampath",  
    contacts:["011-1234567","011-7654321"],  
    [Symbol.iterator]() {  
        let i = 0;  
        return{  
            next() {  
                return{  
                    value: employee.contacts[i],  
                    done:employee.contacts.length === i++  
                }  
            },  
        }  
    }  
}  
  
function executor(resolve,reject){  
    setTimeout(()=>{  
        resolve(employee);  
  
    },5000);  
}  
  
const promiseRef = new Promise(executor);  
  
for(const contact of await promiseRef) console.log(contact);
```

how to use `for..await..of` ->

Values come to the iterator later, but iterator comes without any delay

```Js
const promiseRef1 = new Promise(function (resolve, reject) {  
    setTimeout(function () {  
            resolve({  
                id: "C001",  
                name: "Kasun Sampath"  
            })  
        }, 2000);  
});  
  
const promiseRef2 = new Promise(function (resolve, reject) {  
    setTimeout(function () {  
        resolve({  
            id: "C002",  
            name: "Nuwan Ramidu"  
        })  
    }, 4000);  
});  
  
const promiseRef3 = new Promise(function (resolve, reject) {  
    setTimeout(function () {  
        resolve({  
            id: "C003",  
            name: "Upul Tharanga"  
        })  
    }, 6000);  
});  
  
  
async function* asyncGenerator() {  
    const customer1 = await promiseRef1;  
    yield customer1;  
    const customer2 = await promiseRef2;  
    yield customer2;  
    const customer3 = await promiseRef3;  
    yield customer3;  
}  
  
for await (const value of asyncGenerator()) console.log(value);
```

How to use `for..await..of..await[await promiseRef]`

Both iterator and values come with a delay

```Js
const promiseRef1 = new Promise(function (resolve, reject) {  
    setTimeout(function () {  
            resolve({  
                id: "C001",  
                name: "Kasun Sampath"  
            })  
        }, 2000);  
});  
  
const promiseRef2 = new Promise(function (resolve, reject) {  
    setTimeout(function () {  
        resolve({  
            id: "C002",  
            name: "Nuwan Ramidu"  
        })  
    }, 4000);  
});  
  
const promiseRef3 = new Promise(function (resolve, reject) {  
    setTimeout(function () {  
        resolve({  
            id: "C003",  
            name: "Upul Tharanga"  
        })  
    }, 6000);  
});  
  
  
async function* asyncGenerator() {  
    const customer1 = await promiseRef1;  
    yield customer1;  
    const customer2 = await promiseRef2;  
    yield customer2;  
    const customer3 = await promiseRef3;  
    yield customer3;  
}  
  
const promiseRef =  new Promise(function (resolve,reject) {  
    setTimeout(function () {  
        resolve(asyncGenerator());  
    },5000)  
});  
  
for await (const value of (await promiseRef)) console.log(value);
```

