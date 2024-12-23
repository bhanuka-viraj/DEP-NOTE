

|                                                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ----------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Does js has classes                                                           | No. Java Script does not have  Classes. But they have  implemented class like feature that gives developer to  <br>class feeling similar to the other languages like Java.<br><br>Class is behave as a Constructor.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| What are the <br>characteristic of<br>Classes                                 | 1. Classes are in `strict-mode`<br>2. Constructor functions are created using the function <br>literal. So this is hoisted. it is allowed to access to <br>constructor even before it's declaration. But Classes are <br>lexical declarations. The it is not allowed to access them<br>before declare them.<br>3. Allow to add static initializer, not instance initializer.<br>4. Static Initializer is executed when the class is loaded.<br>==when the constructor object is created==<br>(note the execute)<br>5. Static variables can be created in classes<br>6. Static variables are not allowed to access using instance<br>Only Allow to do that using Constructor function (class)<br>7. Static things are created withing the constructor <br>function. That is why it is unable to reach the static <br>variable using the instance<br>8. Static methods are allowed to created withing the calssess<br> |
| What are the<br>members that can <br>be in the class                          | fields<br>static fields<br>static initializers<br>constructor(only one)<br>Instance methods<br>Static Methods                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| How constructor<br>behave in js                                               | There is a invisible line after the super ( ) same as java. <br>When it is executed instance variables are initialized.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| What happen if <br>there is no <br>constructor is <br>defined                 | A no args constructor is created                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Is this a constructor function                                                | ![[Pasted image 20240606175203.png]]<br>Yes. But cannot be access before it is declared                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| is it allowed to assign <br>to a variable                                     | Yes. Since class is a function it can be assigned to a <br>varaible. When it is assigned no need of name for <br>the class. And this is called class expression<br><br>![[Pasted image 20240606175613.png]]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| What is the difference <br>between `class literal` <br>and `class expression` | This is a class literal<br><br>![[Pasted image 20240606175646.png]]<br><br>This is a  class expression<br>![[Pasted image 20240606175633.png]]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |


How to create classes in Js?

```js
class Customer {  
    id;  
    name;  
  
    constructor(id,name) {  
        this.id = id;  
        this.name = name;  
    }  
  
    print() {  
        console.log(this.id, this.name);  
    }  
}  
  
console.log(typeof Customer);  
console.log(Customer.prototype.constructor == Customer);  
  
const c1 = new Customer("1", "Kasun");  
console.log(c1.__proto__ == Customer.prototype);  
c1.print();  
console.log(Customer instanceof Function);
```

How to use private in classes (using # notation)
```js
class Customer {  
    #id;  
    #name;  
  
    constructor(id, name) {  
        this.#id = id;  
        this.#name = name;  
    }  
  
    print() {  
        this.#privateMethod();  
    }  
  
    #privateMethod() {  
        console.log(this.#id, this.#name);  
    }  
  
}  
  
const c1 = new Customer(1, 'Kasun');  
c1.print();  
const c2 = new Customer(2, "Nimal");  
c2.print();
```

##### Inheritance Using Js
```Js
class ParentClass {  
    a;  
    b;  
  
    constructor(a, b) {  
        console.log("Parent");  
        this.a = a;  
        this.b = b;  
    }  
}  
  
class ChildClass extends ParentClass {  
    c;  
    d=(()=>{  
        console.log("D is being initialized");  
    })();  
  
    constructor(a, b,c,d) {  
        super(a, b);  
        //invisible line here  
        console.log("Child");  
        this.c=c;  
        this.d=d;  
    }  
}  
new ChildClass(1,3,2,4);
```
