
|                                                               |                                                                                                                                                                                                           |
| ------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| How to change<br>the `this` in a function                     | `call(this?,arg1,arg2,arg3)`<br>`apply(this?,[arg1,arg2,arg3])`<br>`bind(this?)`<br><br><br>1. Call and apply execute the function after change this<br>2.bind return a new function binding the this<br> |
| Is it allowed to change <br>the `this` of arrow functions     | No. Since it has a lexical this. It is not allowed to change                                                                                                                                              |
| Which functions are not<br>allowed to change the <br>function | 1. Arrow functions (lexical this function)<br>2. This bounded functions (function that return <br>from the  `bind( ))                                                                                     |
| what is delegatoin                                            | Delegation is the OOP concept.<br>(changing the this is a example)<br>                                                                                                                                    |
What is delegation ->
In [object-oriented programming](https://en.wikipedia.org/wiki/Object-oriented_programming "Object-oriented programming"), **delegation** refers to evaluating a member ([property](https://en.wikipedia.org/wiki/Property_(programming) "Property (programming)") or [method](https://en.wikipedia.org/wiki/Method_(computer_programming) "Method (computer programming)")) of one [object](https://en.wikipedia.org/wiki/Object_(computer_science) "Object (computer science)") (the receiver) in the context of another original object (the sender). Delegation can be done explicitly, by passing the responsibilities of the sending object to the receiving object, which can be done in any [object-oriented language](https://en.wikipedia.org/wiki/Object-oriented_language "Object-oriented language"); or implicitly, by the member lookup rules of the language, which requires language support for the feature. Implicit delegation is the fundamental method for behavior reuse in [prototype-based programming](https://en.wikipedia.org/wiki/Prototype-based_programming "Prototype-based programming"), corresponding to [inheritance](https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming) "Inheritance (object-oriented programming)") in [class-based programming](https://en.wikipedia.org/wiki/Class-based_programming "Class-based programming"). The best-known languages that support delegation at the language level are [Self](https://en.wikipedia.org/wiki/Self_(programming_language) "Self (programming language)"), which incorporates the notion of delegation through its notion of [mutable](https://en.wikipedia.org/wiki/Immutable_object "Immutable object") parent [slots](https://en.wikipedia.org/wiki/Slot_(computer_architecture) "Slot (computer architecture)") that are used upon method lookup on self calls, and [JavaScript](https://en.wikipedia.org/wiki/JavaScript "JavaScript"); see [JavaScript delegation](https://en.wikipedia.org/wiki/JavaScript#Delegative "JavaScript").



How to use apply and call to change `this`

```Js
function execute(id ,name) {  
    console.log(this === globalThis);  
    console.log(this);  
    console.log(id, name);  
  
}  
  
const myObj = {  
    id: "C001",  
    name : "Kasun"  
};  
  
// execute.call(myObj, 1, "Kasun");  
execute.apply(myObj, [1, "Kausn"]);
// myObj is the where now this is defined to

```

How to use bind to change the `this`

```Js
function execute(id ,name) {  
    console.log("Executed");  
    console.log(this === globalThis, id, name);  
    console.log(this);  
  
}  
  
const myObj = {  
    id: "C001",  
    name: "Ruwan",  
}  
  
const newFn = execute.bind(myObj);  
newFn.call({}, 1, "Ruwan");  
/*not allowed to change the 'this' of the  
* bounded function*/
```

==What is the this of a function when the function is declared withing a object ->==

Invoker is the `this` of the function when the function is declared within a object->
```js
const customer = {  
    id: "C001",  
    name: "Kasun",  
    print() {  
        console.log(this);  
    },  
}  
  
customer.print();
```

`add code of the index16.js`

```Js
const customer1 = {
    id: "C001",
    name: "Kasun",
    print() {
        console.log(this.id, this.name);
    }
};

const customer2 = {
    id: "C002",
    name: "Ruwan",
    print() {
        console.log("print()");
        console.log(this.id, this.name);
    }
};

customer1.print(); // Logs: C001 Kasun
customer2.print(); // Logs: print() \n C002 Ruwan

customer2.print.call(customer1); // Logs: print() \n C001 Kasun
```


explain what is the invoker of each time.