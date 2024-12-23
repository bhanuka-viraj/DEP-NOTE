```Js
function Customer(id, name) {  
    this.id = id;  
    this.name = name;  
}  
  
const c1 = new Customer("C001", "Kasun Sampath");  
console.log(Customer.prototype === c1.__proto__); /*0xaf10 === 0xaf12*/  
console.log(c1.__proto__.constructor === Customer);/**/  
console.log(typeof c1);/*This is an object*/  
console.log(typeof c1.__proto__);/*This is an object*/  
console.log(typeof Customer);/*This is a function object*/  
console.log("Is c1 and object?", c1 instanceof Object);  
console.log("Is c1.__proto__ an object?", c1.__proto__ instanceof Object);  
console.log("Is Customer an object?", Customer instanceof Object);  
console.log("Is c1 an instance of the customer?", c1 instanceof Customer);
```

Explain this ->
`set this explanatoins to the prototype chain note in below`
Any Constructor Function should have a prototype object. Constructor Function object has the property call prototype and it link the prototype object. Prototype object has the property call constructor and it is linked with the constructor function. 

==Any object has a property call the `_ _ Proto _ _` . It is linked with the prototype of the constructor that is used to create the object.==

==There is a built in Constructor function call `Object`.  All other object apart from the function object are created using this `Object`==

==All function objects are created from the `Function` Constructor function object.==

##### Prototype Chain 

*Any Constructor function should have a prototype*

*Constructor function has a property called prototype*

*Prototype has property called a constructor*

*Any Object has a property called `__proto__`. It is linked with the prototype of the constructor that is used to create the object*

*There is a built in Constructor function called Object.All the objects apart from the Constructor object are created using this*

*There is a built in Constructor Function called Function.All Constructor functions are created using this object *
###### Step 1
Creating the empty object
![[Pasted image 20240606130319.png]]

 explain this step
###### Step 2
Changing to Customer, as the new Customer() object, was created by Customer

![[Pasted image 20240606130402.png]]


###### Function Object Constructor
There is another built in Constructor Function Object used to create function objects. It is Function.
![[Pasted image 20240606133228.png]]

`call ( )`  and `construct( )` methods are available only in  Function objects

![[Pasted image 20240606133407.png]]

```Js
function Customer(id, name) {
    this.id = id;
    this.name = name;
}

const c1 = new Customer("C001", "Kasun Sampath");
console.log(Customer.prototype === c1.__proto__); //true
console.log(c1.__proto__.constructor === Customer); //true
console.log("c1", typeof c1); //c1 object
console.log("c1.__proto__:", typeof c1.__proto__); //c1.__proto__: object
console.log("Customer :", typeof Customer); //Customer : function
console.log("Is c1 an object?", c1 instanceof Object); //Is c1 an object? true
console.log("Is c1.__proto__ an object?", c1.__proto__ instanceof Object); //Is c1.__proto__ an object? true
console.log("Is Customer an object?", Customer instanceof Object); //Is Customer an object? true
console.log("Is c1 an instance of Customer?", c1 instanceof Customer); //Is c1 an instance of Customer? true

const myObj = new Object();
const myObj2 = {}; //Object Initializer , Object Literal
console.log(myObj, myObj2); //{} {}

myObj.id = "C001";
myObj.name = "Kasun";
console.log(myObj); //{ id: 'C001', name: 'Kasun' }

myObj2.id="C002";
myObj2.name = "Ruwan";
console.log(myObj2); //{ id: 'C002', name: 'Ruwan' }

console.log(Customer.prototype.__proto__ === Object.prototype); //true
console.log(Object.prototype.constructor === Object); //true
console.log(Object.prototype.__proto__); //null
console.log(Customer.__proto__ === Function.prototype); //true
console.log(Object.__proto__ === Function.prototype); //true
console.log(Customer.__proto__ === Object.__proto__); //true
console.log(Customer.__proto__.constructor === Function); //true
console.log(Object.__proto__.constructor === Function); //true
console.log(Function.__proto__ === Function.prototype); //true
console.log(typeof Customer); //function
console.log(typeof Object); //function
console.log(typeof Function); //function
console.log(Customer instanceof Function); // true
console.log(Object instanceof  Function); // true
console.log(Customer instanceof Object); // true
```





Difference of objects in Java and Js

![[Pasted image 20240606144000.png]]

|                                                                     |                                                             |
| ------------------------------------------------------------------- | ----------------------------------------------------------- |
| Does Js allow to <br>create multiple <br>constructors like <br>java | No. It is not allowed to create multiple constructors in js |
