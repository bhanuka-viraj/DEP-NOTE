Example 1 ->
###### Step 1
 link the prototype of the super Constructor function
 ![[Pasted image 20240606142546.png]]
```js
function Car(frameNo, Model) {  
    this.frameNo = frameNo;  
    this.Model = Model;  
}  
  
Car.prototype.breack = function () {  
    console.log("Car is breaking")  
};  
  
Car.prototype.drive = function () {  
    console.log("Drive")  
}  
  
Car.prototype.horn = function () {  
    console.log("Horn")  
}  
  
Car.prototype.shiftGears = function () {  
    console.log("Shift Gears")  
}  
  
function Prius(color, frameNo, Model) {  
    this.color = color;  
    this.frameNo = frameNo;  
    this.Model = Model;  
}  
  
Prius.prototype.__proto__ = Car.prototype;  
  
Prius.prototype.enableEv = function () {  
    console.log("Enable Ev");  
};  
  
const p1 = new Prius("white", "123", "nph");  
console.log(p1);
```

###### Step 2
add the super constructor invocation at the sub constructor invocation's first line
![[Pasted image 20240606142826.png]]

```js
function Car(frameNo, Model) {  
    this.frameNo = frameNo;  
    this.Model = Model;  
}  
  
Car.prototype.breack = function () {  
    console.log("Car is breaking")  
};  
  
Car.prototype.drive = function () {  
    console.log("Drive")  
}  
  
Car.prototype.horn = function () {  
    console.log("Horn")  
}  
  
Car.prototype.shiftGears = function () {  
    console.log("Shift Gears")  
}  
  
function Prius(color, frameNo, Model) {  
    Car(frameNo, Model);  
    this.color = color;  
    // this.frameNo = frameNo;  
    // this.Model = Model;}  
  
Prius.prototype.__proto__ = Car.prototype;  
  
Prius.prototype.enableEv = function () {  
    console.log("Enable Ev");  
};  
  
const p1 = new Prius("white", "123", "nph");  
console.log(p1);
```

###### Step 3
Set the `this` of the Super constructor function same as the sub constructor function 

Otherwise `this` of the super constructor will not take the Prius object
(in here it takes the global)
![[Pasted image 20240606142951.png]]

```js
function Car(frameNo, Model) {  
    this.frameNo = frameNo;  
    this.Model = Model;  
}  
  
Car.prototype.breack = function () {  
    console.log("Car is breaking")  
};  
  
Car.prototype.drive = function () {  
    console.log("Drive")  
}  
  
Car.prototype.horn = function () {  
    console.log("Horn")  
}  
  
Car.prototype.shiftGears = function () {  
    console.log("Shift Gears")  
}  
  
function Prius(color, frameNo, Model) {  
    Car.call(this,frameNo, Model);  
    this.color = color;  
    // this.frameNo = frameNo;  
    // this.Model = Model;}  
  
Prius.prototype.__proto__ = Car.prototype;  
  
Prius.prototype.enableEv = function () {  
    console.log("Enable Ev");  
};  
  
const p1 = new Prius("white", "123", "nph");  
console.log(p1);
```

Example 2 ->

![[Pasted image 20240607015830.png]]

```Js
function User(id, fullName) {
    console.log("User()");
    this.id = id;
    this.fullName = fullName;
}

User.prototype.print = function () {
    console.log("id=", this.id, "full name=", this.fullName);
}

function System(id, fullName, email) {
    User.call(this, id, fullName);
    console.log("System()");
    this.email = email;
}

System.prototype.__proto__ = User.prototype;

System.prototype.print = function () {
    // console.log("id=", this.id, "full name=", this.fullName, "email:", this.email);
    User.prototype.print.call(this);
    console.log("email:", this.email);
}

function Employee(id, fullName, address, contact) {
    User.call(this, id, fullName);
    console.log("Employee()");
    this.address = address;
    this.contact = contact;
}

Employee.prototype.__proto__ = User.prototype;

Employee.prototype.print = function () {
    // console.log("id=", this.id, "full name=", this.fullName, "address:", this.address, "contact:", this.contact);
    /* calling super class method */
    User.prototype.print.call(this);
    console.log("address:", this.address, "contact:", this.contact);
}

function Manager(id, fullName, address, contact, qualifications) {
    Employee.call(this, id, fullName, address, contact);
    console.log("Manager()");
    this.qualifications = qualifications;
}

Manager.prototype.__proto__ = Employee.prototype;

// const user = new User(1, "Kasun");
// user.print();

// const employee = new Employee(1, "Kasun", "Galle", "071-6950532");
// employee.print();

const manager = new Manager(1, "Kasun", "Galle", "071-6950532", "CIMA");
manager.print();
```
